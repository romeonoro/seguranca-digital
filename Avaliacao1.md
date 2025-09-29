- O que é um Malware?
> É um software malicioso projetado para executar ações indesejadas ou danosas em sistemas computacionais.<br>
Exemplos: vírus, worms, trojans, ransomware, spyware e adware. Os objetivos comuns incluem roubo de dados, controle remoto, espionagem, criptografia de arquivos para resgate e degradação de serviços.

- Descreva o processo de conexão TCP e como pode ser utilizada para uma invsasão?
>  three-way handshake <br>
> 1. SYN — o cliente envia um pacote SYN ao servidor pedindo conexão.
> 2. SYN‑ACK — o servidor responde com SYN‑ACK (confirmação do SYN e pede sincronização).
> 3. ACK — o cliente envia ACK final; a conexão fica estabelecida e começa a troca de dados. <br>

> Um atacante pode usar conexões TCP legítimas para estabelecer canais de comunicação (por exemplo, um cliente malicioso que inicia uma sessão com um servidor comprometido para receber comandos), aproveitando o fato de que conexões estabelecidas passam por firewalls de forma diferente de tráfego não solicitado. Ataques como SYN flood exploram o próprio processo de handshake, enviando muitos SYNs sem completar o handshake para esgotar recursos do servidor (negação de serviço).

- O que é um Deepfake?
> É uma mídia sintética (vídeo, áudio, imagem) criada com IA que substitui ou altera a identidade de pessoas (por exemplo, trocar um rosto em um vídeo ou clonar uma voz). Pode ser usado para entretenimento legítimo, mas também para desinformação, fraude e difamação.

- O que significa DDNS e como ele funciona? Pode dar um exemplo para explicar.

- Qual a diferença de Phreakers e Defacers?
> Phreakers: exploravam sistemas de telefonia para obter chamadas gratuitas, manipular centrais ou explorar vulnerabilidades da rede telefônica. <br>
Defacers: atacantes que alteram o conteúdo de sites — normalmente substituindo a página inicial por uma mensagem, imagem ou propaganda. É um tipo de vandalismo digital voltado a sites/webservers.

- Explique o que é zona de DNS e por que ocorre sua transferência?
> Uma zona é um conjunto de registros, porção do espaço de nomes DNS para a qual um servidor DNS (autoritativo) é responsável. Numa zona estão registros como A, AAAA, MX, NS, TXT, etc. <br>
Transferências de zona são realizadas para replicar os dados da zona do servidor primário (master) para servidores secundários (slave). Motivos:
>  - redundância e disponibilidade (se o primário cair, secundários continuam respondendo);
>  - balanceamento de carga;
>  - backup e distribuição geográfica.

- Como funciona o Algoritmo PageRank?
> Mede a importância de páginas web com base na estrutura de links.
<img width="4000" height="2878" alt="image" src="https://github.com/user-attachments/assets/432555ee-deb0-4a55-9035-23c0558b5b5a" />

- Quando e onde surgiu o termo "Hacker"?
> Surgiu nas décadas de 1950 e 1960, no Massachusetts Institute of Technology (MIT)

- Como podemos verificar quais os servidore de DNS o nosso sistema operacional Linux está utilizando?
> cat /etc/resolv.conf — mostra servidores DNS configurados tradicionalmente.

- O que garante que o trabalho de um Hacker ético, não seja considerado um crime?
> O que diferencia um hacker ético de um crime é autorização legal e *contratual*.

- Quando o servidor secundário de DNS é acionado?
> Resumidamente, servidores secundários (slaves) são usados sempre que um resolvedor consultando a zona autoritativa escolher qualquer nameserver autoritativo disponível — se o primário (master) não responder, os resolvers podem consultar os secundários. Além disso, secundários servem requests normalmente (balanceamento/alta disponibilidade). Internamente, secundários obtêm/atualizam dados do primário via transferências de zona (AXFR/IXFR); se o primário estiver indisponível, o secundário continua respondendo com os dados que já tem até expirarem (TTL ou SOA expiration).

- O que esta consulta irá retornar, de acordo com o Google Hacking? Site;com.br filetype:txt intext:senhas
> Essa consulta procura por arquivos .txt em domínios .com.br que contenham a palavra "senhas" no texto.

- Cite três formas de descobrir o sevidor de DNS de um serviço hospedado na WWWW:


2 - processo conexão tcp e como pode ser usada para uma invasão?
3 handshake, cliente servidor syn -> ack/syn <- ack ->
estabelece uma conexão e não encerra

4 - ddns e como funciona? exemplo 
camera de segurança, baba eletrônica

6 - zona de dns e pq ocorre sua transferência?

14 - host, dnslookup, whatsmyip, whois, dnsdumpster.com
