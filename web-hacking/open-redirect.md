# Open Redirect

Open redirect é uma vulnerabilidade web que redireciona usuários para URL maliciosas sem avisar o usuário que ele vai ser redirecionado.\
\
Vulnerabilidade útil para ser utilizada em ataques de phishing, exemplo:\
\
https://nubank.com.br/?redirect=<mark style="color:red;">https://SITEFAKE.com.br</mark>\
\
Com isso, podemos criar uma replica do site do nubank para adquirir credenciais de acesso do usuário.
