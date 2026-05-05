# SSRF - para Metadados da AWS

A **Server-Side Request Forgery (SSRF)** é uma vulnerabilidade de segurança que permite a um atacante induzir uma aplicação do lado do servidor a fazer requisições HTTP (ou outras) arbitrárias para recursos internos ou externos, muitas vezes sem o conhecimento do servidor. Quando essa vulnerabilidade é explorada em um ambiente da Amazon Web Services (AWS), ela se torna particularmente perigosa devido à forma como a AWS expõe **metadados** importantes sobre as instâncias EC2.

{% embed url="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instancedata-data-retrieval.html" %}

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

**Report na HackerOne dessa vuln:**

> [https://hackerone.com/reports/1108418](https://hackerone.com/reports/1108418)
>
> #### Vulnerabilidade SSRF no Streamlabs Cloudbot
>
> 1. **Variável `readapi`:** O Streamlabs Cloudbot possui uma funcionalidade que permite aos usuários incorporar conteúdo de URLs externas nas respostas do chat, utilizando a variável `readapi`. Isso significa que o servidor do Cloudbot faz uma requisição para o URL fornecido pelo usuário e inclui o resultado na resposta.
> 2. **Problema com Redirecionamentos:** O ponto crucial da vulnerabilidade era que, embora o Cloudbot forçasse o uso de HTTPS para as requisições iniciais, ele **seguia redirecionamentos**, mesmo que esses redirecionamentos apontassem para URLs HTTP.
> 3. **Exploração e Metadados da AWS:** Um atacante explorou essa característica da seguinte forma:
>    * Ele fornecia um URL HTTPS válido que, por sua vez, redirecionava para o endpoint HTTP do serviço de metadados da AWS: `http://169.254.169.254/latest/meta-data/`.
>    * Como a requisição era feita do lado do servidor (pelo Streamlabs Cloudbot), e o servidor estava rodando em uma instância EC2 da AWS, ele conseguia acessar o endpoint interno de metadados.
>    * Ao seguir o redirecionamento para o endereço `169.254.169.254`, o atacante conseguia obter informações sensíveis sobre a instância EC2, como credenciais de segurança temporárias (IAM roles), endereços IP e outras configurações.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Tools para explorar essa vuln por completo:



Tool Pacu - AWS exploitation framework

{% @github-files/github-code-block url="https://github.com/RhinoSecurityLabs/pacu" %}

AWS CLI

{% embed url="https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html" %}





