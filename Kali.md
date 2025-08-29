cat = concatena

vi dominios.lst

# Anotações sobre Linux, Permissões e Scripts

## 📝 Criando e editando arquivos com `vi`

O comando `vi nomedoarquivo` serve para criar ou editar arquivos no Linux.  
É semelhante ao `nano`, mas **mais poderoso** e com funcionalidades avançadas.

### 🧠 Dentro do `vi`:

- `i` → modo **insert** (para começar a escrever)
- `Esc` → sai do modo de inserção
- `:` → abre o modo de **comando**
  - `:w` → salva (write)
  - `:q` → sai (quit)
  - `:wq` → salva e sai

---

## ➡️ Redirecionamento de saída

Para redirecionar a saída de um comando para um arquivo, usamos o símbolo `>`:

```bash
comando > arquivo.txt
