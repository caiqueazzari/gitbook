# XML External Entity Attack - XXE

**XML** significa **eXtensible Markup Language** (Linguagem de Marcação Extensível).\
É uma linguagem usada para **armazenar e transportar dados** de forma estruturada e legível tanto por humanos quanto por máquinas.

```xml
<livro>
  <titulo>XML</titulo>
  <autor>takemoto</autor>
  <ano>2077</ano>
</livro>
```

Um ataque **XXE** é uma vulnerabilidade que ocorre quando um sistema processa dados XML de forma insegura. Ele permite que um atacante injete entidades XML externas maliciosas, podendo causar:

* Divulgação de arquivos confidenciais (ex: `/etc/passwd`)
* Execução de requisições internas (SSRF)
* Ataques de negação de serviço (DoS)
* Em casos extremos, execução remota de código

```xml
<?xml version="1.0"?>
<!DOCTYPE foo [
  <!ELEMENT foo ANY >
  <!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<foo>&xxe;</foo>
```



