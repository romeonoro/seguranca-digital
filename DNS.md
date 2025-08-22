# DevSecOps

**DevSecOps** é a integração das áreas de Desenvolvimento (Dev), Segurança (Sec) e Operações (Ops) em um fluxo contínuo, com foco em automação, monitoramento e segurança desde o início do ciclo de vida do software.

---

# DNS (Domain Name System)

- **Camada**: 7 (Aplicação)
- **Porta**: 53
- **Protocolo**: UDP (Camada 4 - Transporte)
- Em casos específicos pode usar TCP (ex: transferências de zonas)

## Servidores DNS

- **8.8.8.8** – Servidor DNS público do Google  
- **200.132.59.10** – DNS associado à UFN (ex: www.ufn.edu.br)

---

## Exemplo de Requisição DNS

**Objetivo**: A máquina quer acessar `www.ufn.edu.br`

### Informações:

- **IP da máquina**: 10.104.16.3  
- **Máscara de rede**: 255.255.255.192  
- **Gateway padrão**: 10.104.16.1  
- **Servidores DNS**:  
  - Primário: 10.21.19.14  
  - Secundário: 10.21.19.15

### Etapas envolvidas:

1. **ARP (Address Resolution Protocol)**: Resolve MAC do gateway ou DNS
2. **ICMP (Internet Control Message Protocol)**: Pode ser usado para testes (ex: ping)
3. **Requisição DNS**: A máquina envia requisição via porta 53/UDP
4. **Resposta**: DNS responde com o IP correspondente ao domínio requisitado

---

## Perguntas importantes (relacionadas à resolução de nomes):

- **Quem eu sou?**  
  → Verifica seu próprio IP, máscara, gateway, etc.

- **É meu vizinho?**  
  → Determina se o IP de destino está na mesma sub-rede.

---

# DDNS (Dynamic DNS)

- Permite que dispositivos com IPs dinâmicos atualizem automaticamente seus registros DNS.
- Muito usado por serviços residenciais ou pequenos servidores sem IP fixo.

---

# DNS Reverso

- Utiliza registros PTR.
- Permite descobrir o nome de domínio a partir de um endereço IP.
- Exemplo: `10.0.0.1` → consulta PTR → resposta: `server.exemplo.com`

---

# Entidades de Registro

- **Registro.br** – Responsável pelos domínios ".br"
- **Terra** – Pode atuar como provedor de serviços DNS

---

