# SSRF - Protocol Smuggling MYSQL

<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

**SSRF utilizando a técnica de Protocol Smuggling com o protocolo Gopher**

Para explorar uma vulnerabilidade de **SSRF** usando a técnica de **Protocol Smuggling** com o protocolo **Gopher**, é possível utilizar a ferramenta **Gopherus**, que gera o payload necessário em apenas **uma linha**.

Observação: O protocolo **Gopher** só funciona com a ferramenta **curl**.

#### Parâmetros via GET

Quando a vulnerabilidade estiver presente em um **parâmetro GET**, será necessário aplicar **Double URL Encoding** no payload.

**Passo a passo:**

1. Gere o payload utilizando o **Gopherus**.
2. Aplique **Double URL Encoding** no payload gerado:
   * Faça a primeira codificação normalmente;
   * Em seguida, aplique uma segunda codificação, por exemplo, usando o site: [https://www.urlencoder.org/](https://www.urlencoder.org/)
