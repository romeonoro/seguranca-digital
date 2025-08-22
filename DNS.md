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
