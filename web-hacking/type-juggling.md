---
description: Type Juggling em PHP
---

# Type Juggling

**Type juggling** (ou **coerção de tipo**) é um comportamento comum em linguagens de programação de tipagem fraca, como o **PHP**, onde os tipos de dados são convertidos automaticamente pelo interpretador dependendo do contexto

exemplo&#x20;

if ("0e1234" == "0") {\
echo "Iguais!";\
}\
\
E**xemplo de bypass**

```
if ($_POST['password'] == $hash) {
// Acesso concedido
}
```

**Bypass de autenticação com hashes "0e..."**

```
$stored_hash = md5("senha_secreta"); // exemplo: "0e462097431906509019562988736854"
if ($_POST['senha'] == $stored_hash) {
echo "Acesso concedido";
}
```

**O atacante pode fazer:**

```
$input = "240610708"; // md5("240610708") = "0e462097431906509019562988736854"
```

#### **Type juggling com `==` e `===`**

```php
phpCopiarEditar$a = "0e1234";
$b = "0";

var_dump($a == $b);   // true
var_dump($a === $b);  // false
```

Na comparação com `==`, o PHP tenta converter ambos os lados para **números** → `0 == 0`.\
Mas com `===`, ele compara **tipo e valor**, então detecta que um é string e o outro é número.

***

#### **Quebra de verificação em arrays (ex: reset de senha)**

#### Suponha o código:

```php
phpCopiarEditar$user = $_GET['user']; // atacante envia algo
$data = [
    'admin' => 'hash_admin',
    'joao' => 'hash_joao'
];

if (isset($data[$user])) {
    echo "Usuário existe!";
}
```

Se o atacante envia:

```
?user[]=1
```

A variável `$user` vira um **array**, e não uma string. O código `isset($data[$user])` dá um **warning**, mas pode ser **bypassado ou crashar** dependendo do PHP.



<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>



{% file src="../.gitbook/assets/PHP Magic Tricks Type Juggling.pdf" %}



