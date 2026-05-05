# Command Injection

É uma vulnerabilidade de segurança que permite a um atacante injetar e executar comandos arbitrários

Exemplo em app web\
[http://site.com/ping.php?ip=8.8.8.8;whoami<br>](http://site.com/ping.php?ip=8.8.8.8;whoami)O server executaria : ping -c 4 8.8.8.8; whoami







**Tools**

Burp Suite\
OWASP ZAP\
Nikto\
Ferramentas de SAST/DAST\
Commix ferramenta focada em testar command injection

