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

