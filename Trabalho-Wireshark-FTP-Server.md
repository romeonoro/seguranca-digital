# Trabalho monitoramento de ações do Windows utilizando Wireshark no Ubuntu com FTP Server.

> NOME: Matheus Nogueira, Bruno Difante, Romeo Noro

### O monitoramento será vendo as ações do Windows no Filezilla, vendo as credenciais de acesso que ele utilizou, no caso ele entrou com o usuário criado no Ubuntu, e o Ubuntu visualizou essas próprias credenciais que foram digitadas, via Wireshark.

# Passo a Passo

## No UBUNTU

### Instalar o Wireshark

> Para isso, deve-se executar os seguintes comandos para a instalação do Wireshark

```
sudo apt update

sudo apt install wireshark -y
```

> Após instalado, deve-se criar um usuário 

```
sudo adduser matheus



-- E colocar as informações do usuário (usuario - matheus/senha- nogz04), criá-lo e após isso adicionar no grupo de super usuários (SUDO):

sudo usermod -aG sudo matheus



-- E adicionar ao grupo wireshark por precaução:

sudo usermod -aG wireshark matheus



-- Entrar no usuário:

su matheus
```

Após o usuário configurado o usuário, devemos instalar o FTP Server

```txt

sudo apt install vsftpd -y



-- Caso apareça: Waiting for cache lock, espere um pouco e monitore via:

ps aux | grep unattended-upgr



-- Caso o processo já tenha sido concluído, rode novamente isso:

sudo apt update
sudo apt install vsftpd -y



-- Aguarde instalar


```

## Vamos para o Windows

Após isso, instale o filezilla no Windows, abra ele e aguarde a próxima etapa que é a seguinte: <br>

Veja o código da porta do PC Ubuntu e Linux que estão conectados no espelho dos PCs, nesse caso a do Ubuntu é 01A e do Windows é 08A, pegue a outra ponta do cabo do espelho de ambos que estão conectados no Switch, desconecte e conecte no HUB ambas, ficará assim:
Espelho do PC -> HUB conectados, o Linux e Windows. <br>

Com isso feito, irá ser desconectada a internet do PC, você deverá trocar o IPV4 do Windows e Ubuntu para 192.168.10.3 e 192.168.10.5 respectivamente e ambos com máscara 255.255.255.0. <br>

Após isso, no filezilla instalado no Windows, vamos conectar em conexão rápida colocando as seguintes informações

```txt
Host: 192.168.10.5

Nome do usuário: matheus

Senha: nogz04 (nesse caso)

Porta: o filezilla coloca automática, no caso colocou a 21.
```



![FotoFilezilla](https://github.com/user-attachments/assets/9ad2a35d-e55a-47f7-a64b-4f5a2d2897b3)


## No Ubuntu novamente:

Vamos rodar no terminal, dentro do usuário matheus, o comando:

```txt

-- Verificar em qual interface está correspondendo a sua rede com seu ip 192.168.10.5

ip addr


-- Vamos abrir o wireshark:

sudo wireshark

```

Iremos dar 2 cliques sob a interface que você verificou, no caso da minha era: enp0s31f6, e pesquisar por ftp na barra de pesquisa, pronto, aparecerá as ações do Windows, aparecerá que ele se conectou via filezilla com o login (matheus) e senha visiveis(nogz04), podendo ve-las. Isso funciona para qualquer ação, seja outro login por exemplo MySQL, ou qualquer outra ação sem ser login, etc... Em WI-FI ativo, dá para ver diversas ações sem conexão direta estabelecida com outro PC ou Mobile.

### Assim, você estará monitorando as ações do Windows.


![FotoWireshark](https://github.com/user-attachments/assets/69800ad3-4039-4dc7-abc5-67fdfa15738b)


