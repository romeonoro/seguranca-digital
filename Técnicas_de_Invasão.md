## Exploit
Um **exploit** é um código ou técnica usada para **explorar uma vulnerabilidade** em um sistema, software ou serviço.

### Características:
- Explora falhas conhecidas ou desconhecidas (zero-day)
- Pode resultar em acesso não autorizado
- Normalmente depende da versão do software ou do sistema operacional

### Exemplo:
- Explorar uma falha em um serviço desatualizado para executar comandos remotamente.

---

## Payload
O **payload** é o **código executado após o exploit ter sucesso**.

### Função:
- Define o que o atacante fará depois da exploração
- Pode abrir uma shell, criar backdoor, roubar dados, etc.

### Tipos comuns:
- **Reverse Shell**: a vítima se conecta ao atacante
- **Bind Shell**: a vítima abre uma porta aguardando conexão
- **Meterpreter**: payload avançado e interativo

---

## Meterpreter
O **Meterpreter** é um payload avançado usado no Metasploit.

### Principais características:
- Executa na memória (evita antivírus tradicionais)
- Comunicação criptografada
- Não grava arquivos no disco (em muitos casos)

### Funcionalidades:
- Captura de tela
- Keylogger
- Acesso a arquivos
- Escalada de privilégios
- Controle remoto da máquina

---

## Metasploit
O **Metasploit Framework** é uma das principais ferramentas de **pentest** do mundo.

### Utilização:
- Desenvolvimento e execução de exploits
- Testes de invasão controlados
- Estudos de segurança ofensiva

### Estrutura básica:
- **Exploit** → explora a falha
- **Payload** → ação após a invasão
- **Listener** → aguarda conexão da vítima

---

## Invasão por Arquivos `.PDF`
A invasão por PDF explora **falhas em leitores de PDF** (ex: Adobe Reader).

### Como funciona:
- O atacante cria um PDF malicioso
- A vítima abre o arquivo
- O exploit é executado automaticamente
- O payload é ativado (ex: Meterpreter)

### Técnicas usadas:
- JavaScript malicioso embutido
- Exploração de vulnerabilidades antigas
- Engenharia social para induzir a abertura do arquivo

---

## Invasão por Arquivos `.EXE`
Arquivos `.exe` são comuns em ataques por **engenharia social**.

### Como funciona:
- O atacante cria um executável malicioso
- Disfarça como programa legítimo
- A vítima executa o arquivo
- O payload é instalado/executado

### Exemplos:
- "Atualização falsa"
- "Crack de software"
- "Instalador modificado"

---

## Relação com Engenharia Social
Grande parte dessas técnicas depende do **erro humano**:
- Curiosidade
- Falta de conhecimento
- Confiança excessiva

Mesmo sistemas seguros podem ser comprometidos se o usuário executar um arquivo malicioso.

---

## Considerações Éticas
⚠️ Todas essas técnicas devem ser usadas **apenas para fins educacionais ou testes autorizados**.  
O uso sem permissão caracteriza **crime** conforme a legislação brasileira.

---

## Conclusão
- Exploits exploram falhas
- Payloads definem o impacto
- Metasploit integra tudo
- Arquivos PDF e EXE são vetores comuns
- O fator humano continua sendo o elo mais fraco
