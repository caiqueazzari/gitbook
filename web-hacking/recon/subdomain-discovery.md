# Subdomain Discovery

**Histórico de subdomínios, essas ferramentas guardam informações de domínios e subdomínios que já existiram.**&#x20;

* securitytrails.com
* subdomainfinder.c99.nl
* web.archive.org
* dnsdumpster.com
* github.com/Screetsec/Sudomy

**Brute Force**&#x20;

* github.com/aboul3la/Sublist3r
* github.com/TheRook/subbrute
* github.com/OWASP/Amass

**Certificados e passivos**&#x20;

* github.com/projectdiscovery/subfinder - **melhor ferramenta**&#x20;
* sslmate.com/certspotter
* github.com/UnaPibaGeek/ctfr&#x20;
* chaos.projectdiscovery.io

**Comandos CLI**

host - O comando `host` é uma ferramenta que resolve nomes de domínio em endereços IP ou vice-versa

* Localiza o endereço IP de um nome de domínio
* Localiza o nome de domínio associado a um endereço IP
* Exibe aliases associados ao nome de host
* Recupera informações de DNS sobre um nome de host ou domínio

`host [-a] [-c Class ] [-d ] [-r ] [-t Type ] [-v ] [-w ] Hostname | Address [ Server ]`

**Podemos criar um script para enumerar subdominios com esse comando.**

lista.txt\
app\
login\
register\
ha

`for subdominio in $(cat lista.txt); do echo "Testando $subdominio.nubank.com.br"; host $subdominio.nubank.com.br | grep -v 'NXDOMAIN'; done;`

**Listas de subdominios**

* SecLists\
  [https://github.com/danielmiessler/SecLists/tree/master/Discovery/DNS](https://github.com/danielmiessler/SecLists/tree/master/Discovery/DNS)\
  [https://raw.githubusercontent.com/danielmiessler/SecLists/refs/heads/master/Discovery/DNS/shubs-subdomains.txt](https://raw.githubusercontent.com/danielmiessler/SecLists/refs/heads/master/Discovery/DNS/shubs-subdomains.txt)
