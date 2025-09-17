# Protocolos de Exclusão de Robôs

## 📌 O que é
O **protocolo de exclusão de robôs** (Robots Exclusion Protocol – **robots.txt**) é um **padrão de comunicação entre sites e crawlers/bots** (como Googlebot, Bingbot, etc.), criado para **indicar quais partes de um site podem ou não ser acessadas e indexadas** por mecanismos de busca e outros robôs automatizados.

Ele **não é uma regra obrigatória**, mas sim uma **orientação**: os bots legítimos (como buscadores) respeitam o protocolo, mas bots maliciosos podem ignorá-lo.

---

## 📌 Para que serve
- **Controle de indexação**: evitar que páginas específicas apareçam em resultados de busca (ex: páginas de teste, duplicadas ou privadas).  
- **Economia de recursos**: impedir que robôs acessem áreas pesadas ou irrelevantes, poupando banda e processamento do servidor.  
- **Organização de SEO**: direcionar os buscadores para o conteúdo mais relevante.  
- **Segurança básica**: evitar exposição desnecessária de diretórios (embora não substitua medidas reais de segurança).

---

## 📌 Como funciona
O controle é feito por meio de um arquivo chamado **`robots.txt`**, colocado **na raiz do site** (exemplo: `https://www.exemplo.com/robots.txt`).  

Esse arquivo contém regras em formato simples:

```txt
User-agent: *
Disallow: /admin/
Disallow: /privado/

User-agent: Googlebot
Allow: /blog/
Disallow: /teste/
```

- `User-agent:` define a qual bot a regra se aplica (`*` = todos).  
- `Disallow:` bloqueia diretórios ou páginas.  
- `Allow:` permite acesso (útil quando um diretório é bloqueado, mas há exceções).  

---

## 📌 Onde se utiliza
- **Sites e portais**: para organizar SEO e evitar indexação de partes internas.  
- **E-commerces**: bloqueando páginas de carrinho, filtros ou sessões de usuário.  
- **Sistemas web**: para impedir que áreas administrativas ou de teste sejam varridas por bots.  
- **APIs e serviços online**: quando não se deseja indexação automática.  

Além disso, buscadores também consultam o arquivo **`sitemap.xml`** (muitas vezes indicado dentro do `robots.txt`) para descobrir páginas que devem ser indexadas.

---

👉 **Resumindo**: o **protocolo de exclusão de robôs** é uma forma de **dialogar com crawlers**, dizendo o que pode ou não ser explorado, melhorando o desempenho do site e a relevância nos buscadores.
