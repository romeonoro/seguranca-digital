# Anotações sobre Linux, Permissões e Scripts

## 📂 Permissões de arquivos no Linux

As permissões são divididas em três categorias:

- owner (dono do arquivo)
- group (grupo)
- others (outros usuários)

| Número | Letra | Significado |
| ------ | ----- | ----------- |
| 1      | x     | execute     |
| 2      | w     | write       |
| 4      | r     | read        |

## 📁 Arquivos .lst

Arquivos com extensão .lst geralmente são listas de dados ou saídas de comandos gravadas em texto.
Eles são usados, por exemplo, para armazenar domínios, nomes de arquivos, comandos, ou resultados de scripts.



cat dominios.lst


> O comando cat concatena e exibe o conteúdo do arquivo no terminal.

---

## 📝 Criando e editando arquivos com `vi`

O comando `vi nomedoarquivo` serve para criar ou editar arquivos no Linux.  
É semelhante ao `nano`, mas **mais poderoso** e com funcionalidades avançadas.

### 🧠 Dentro do `vi`:

- `i` → modo **insert** (para começar a escrever)
- `Esc` → sai do modo de inserção
- `:` → abre o modo de **comando**
  - `:w` → salva (write)
  - `:q` → sai (quit)
  - `:wq!` → salva e sai (forçando, se necessário)

---
Um endereço IP que começa com
169.254 é um endereço IP link-local que pode ter duas funções principais: 

    Indica uma falha na rede: Quando um dispositivo não consegue obter um endereço IP de um servidor DHCP (como o do seu router), ele atribui automaticamente um endereço 169.254.x.x para comunicação na rede local, mas não pode aceder à Internet.
