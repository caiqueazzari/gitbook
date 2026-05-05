# Métodos HTTP

* **GET:**&#x55;tilizado para recuperar informações de um recurso, como uma página web ou um arquivo. A requisição GET é segura e idempotente, o que significa que não modifica o estado do servidor e pode ser repetida sem problemas.&#x20;
* **POST:**&#x55;tilizado para enviar dados para o servidor, como formulários ou dados de login. Pode ser usado para criar novos recursos ou modificar os existentes. A requisição POST não é idempotente e pode causar alterações no estado do servidor.&#x20;
* **PUT:**&#x55;tilizado para substituir um recurso existente completamente. O servidor deve substituir o recurso por completo com a nova representação fornecida na requisição.&#x20;
* **PATCH:**&#x55;tilizado para modificar parcialmente um recurso existente. O servidor deve atualizar apenas as partes do recurso que foram alteradas na requisição.&#x20;
* **DELETE:**&#x55;tilizado para apagar um recurso do servidor.&#x20;
* **HEAD:**&#x53;emelhante ao GET, mas apenas retorna os cabeçalhos da resposta, sem o corpo. É usado para obter informações sobre um recurso, como o tamanho do arquivo ou o tipo de conteúdo.&#x20;
* **OPTIONS:**&#x55;tilizado para obter informações sobre os métodos HTTP suportados por um recurso. É usado para descobrir quais métodos podem ser usados para interagir com o recurso.&#x20;
* **TRACE:**&#x55;tilizado para depurar problemas de rede, permitindo que o cliente veja a rota da requisição.&#x20;
* **CONNECT:**&#x55;tilizado para estabelecer uma conexão tunelada com um servidor.&#x20;

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



{% embed url="https://www.rfc-editor.org/rfc/rfc9110.html" %}
