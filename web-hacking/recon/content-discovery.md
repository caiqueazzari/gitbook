# Content Discovery

**Ferramentas:**

* github.com/projectdiscovery/httpx - **essa ferramenta verifica se o endereço corresponde a um servidor web e qual status code está sendo retornado pelo subdomínio/domínio. Também realiza varredura de portas, caso necessário.**
* github.com/michenriksen/aquatone
* github.com/m4ll0k/SecretFinder

**`subfinder -d nubank.com.br  -silent`**` ``| httpx`**`-silent`**` ``| gau`&#x20;

Discovery de subdominios (subfinder), validação se o servidor tem uma aplicação web (httpx) e depois decobrir endereços de URLs dentro desses subdomínios (gau).

^ comando rápido para recon em domínio&#x20;

**Como utilizar aquatone:**\
`subfinder -d nubank.com.br -silent | ./aquatone`&#x20;

aquatone é uma ferramenta que tira screenshots de todos os subdomínios e gera um relatório em html contendo todas as informações, tecnologias rodando no site e screenshots
