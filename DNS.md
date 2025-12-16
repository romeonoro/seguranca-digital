# DevSecOps

**DevSecOps** é a integração das áreas de Desenvolvimento (Dev), Segurança (Sec) e Operações (Ops) em um fluxo contínuo, com foco em automação, monitoramento e segurança desde o início do ciclo de vida do software.

---

# DNS (Domain Name System)

- **Camada**: 7 (Aplicação)
- **Porta**: 53
- **Protocolo**: UDP (Camada 4 - Transporte)
  - Em alguns casos pode usar TCP (ex: transferências de zona)

## Servidores DNS

- **8.8.8.8** – Servidor DNS público do Google
- **200.132.59.59** (Primário) – DNS da UFN
- **200.132.59.60** (Secundário) – DNS da UFN
- **200.132.59.110** – IP do site institucional da UFN
- **Proxy/Firewall**: 200.132.59.110.2 *(verificar se IP está correto – possível erro de formatação)*

---

## Exemplo de Requisição DNS

**Objetivo**: A máquina quer acessar `www.ufn.edu.br`

### Informações da Máquina:

- **IP**: 10.104.16.3  
- **Máscara de rede**: 255.255.255.192  
- **Gateway padrão**: 10.104.16.1  
- **Servidores DNS configurados**:
  - Primário: 10.21.19.14
  - Secundário: 10.21.19.15

### Etapas envolvidas:

1. **ARP** – Resolve o MAC do gateway ou servidor DNS.
2. **ICMP** – Pode ser utilizado para testes de conectividade (ping).
3. **Requisição DNS** – A máquina envia uma solicitação via porta 53/UDP.
4. **Resposta DNS** – O servidor retorna o IP correspondente ao domínio (`www.ufn.edu.br` → 200.132.59.110).

---

## Perguntas importantes (durante resolução de rede):

- **"Quem eu sou?"**  
  → Refere-se à identificação do IP da própria máquina.

- **"É meu vizinho?"**  
  → Verifica se o IP de destino está na mesma sub-rede, com base na máscara de rede.

---

# DDNS (Dynamic DNS)

- Permite a atualização automática de registros DNS para hosts com IP dinâmico.
- Muito utilizado por serviços residenciais e pequenos servidores sem IP fixo.

---

# DNS Reverso

- Utiliza registros do tipo **PTR**.
- Permite descobrir o **nome de domínio** associado a um determinado **endereço IP**.
- Exemplo: `200.132.59.110` → consulta PTR → resposta: `www.ufn.edu.br`

---

# Entidades de Registro

- **Registro.br** – Responsável pela administração de domínios ".br"
- **Terra** – Pode atuar como provedor de DNS ou serviços de hospedagem

---

# Resumo: DNS Completo e Reconhecimento

Este documento resume os principais conceitos sobre DNS, tipos de registros, scripts de reconhecimento e ferramentas de análise de vulnerabilidades.

## 1. Fundamentos do DNS (Domain Name System)
O DNS é um sistema hierárquico e descentralizado, em uso desde 1985, essencial para a funcionalidade da Internet.
* **Função:** Traduz nomes de domínio (fáceis de memorizar) para endereços IP numéricos necessários para localizar serviços e dispositivos.
* **Fluxo de Consulta:**
    1.  O usuário consulta um nome (ex: `www.ufn.edu.br`).
    2.  Um **Solucionador Recursivo** (geralmente do ISP) recebe a consulta.
    3.  Ele contacta um **Servidor Root** para obter informações sobre o domínio de topo (TLD), como `.br`.
    4.  O servidor **TLD** responde com o IP do servidor de nomes do domínio específico.
    5.  O **Servidor de Nomes de Domínio** final entrega o IP completo ao solucionador.

## 2. Tipos de Registros e DDNS
O sistema utiliza diversos registros para associar informações aos domínios.
* **DDNS (Dynamic DNS):** Método para atualizar automaticamente um servidor de nomes com endereços IP dinâmicos, permitindo acesso a equipamentos como câmeras IP e serviços como TeamViewer.
* **Principais Registros:**
    * **A:** Endereço IPv4.
    * **AAAA:** Endereço IPv6.
    * **CNAME:** Alias (apelido) de domínio.
    * **MX:** Mail Exchange (servidores de e-mail).
    * **NS:** Name Server (servidor de nomes).
    * **SOA:** Start of Authority (contém e-mail do administrador, tempos de atualização e última atualização da zona).

## 3. Reconhecimento (Recon) e Scripts
O uso de ferramentas para consultar o DNS permite identificar vulnerabilidades e mapear a infraestrutura.

### Ferramenta `host` (Kali Linux)
* **Consulta Básica:** `host dominio.com` retorna o endereço IP e o servidor de correio.
* **Consulta de NS:** `host -t NS dominio.com` exibe os servidores de nomes (Name Servers) onde o domínio está hospedado.

### Scripts de Força Bruta (Bash)
Para agilizar o processo, utilizam-se scripts para descobrir subdomínios e mapear a rede.

1.  **Força Bruta de Subdomínios:**
    * Cria-se uma lista de palavras (`dominios.lst`) com nomes comuns como `www`, `mail`, `ftp`.
    * O script itera sobre a lista testando `palavra.dominio` para encontrar IPs válidos.
    * Pode revelar painéis administrativos ou servidores internos (ex: `painel.terra.com.br`).

2.  **DNS Reverso (Força Bruta):**
    * O DNS reverso faz o caminho contrário: dado um IP, descobre o nome de domínio associado.
    * O script varre o último octeto de um IP (0 a 255) para encontrar nomes associados.
    * É necessário aplicar a varredura apenas no último octeto para evitar endereços inválidos (IPv4 tem 32 bits, não 40).

## 4. Transferência de Zonas de DNS
A transferência de zona replica os dados de DNS entre servidores, mas pode ser explorada se mal configurada.

* **Tipos de Servidores:**
    * **Primário (Master):** Mantém a base de dados original e tem autoridade sobre a zona.
    * **Secundário (Slave):** Cópia do primário, usada se o master falhar.
    * **Caching:** Apenas guarda consultas em cache para performance, sem autoridade sobre zonas.
* **A Vulnerabilidade:** Administradores podem configurar transferências inseguras, permitindo que qualquer pessoa baixe todos os registros do domínio com o comando `host -l`.
* **Comando:** `host -l dominio.com ns.servidor.com`.
* **Segurança:** Se bem configurado, o servidor retornará `REFUSED` ou `Transfer failed`. Se vulnerável, listará todos os subdomínios e IPs.

## 5. Ferramentas Automatizadas
O Kali Linux possui ferramentas que automatizam a coleta de dados.

* **Dnsenum:**
    * Enumera endereços de host, servidores de nomes e registros MX.
    * Tenta realizar transferências de zona automaticamente.
* **DMitry (Deepmagic Information Gathering Tool):**
    * Aplicativo em linha de comando codificado em C para reunir o máximo de dados possível sobre um alvo.
    * **Funcionalidades:** Busca subdomínios (`-s`), endereços de e-mail (`-e`), scan de portas TCP (`-p`), informações de uptime e whois.
