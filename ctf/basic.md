# Basic

nmap -sC -sV IP

rustscan -a IP&#x20;

curl -I IP

echo domain IP > /etc/hosts&#x20;



Fuzzing subdomains

ffuf -c -u URL -H "Host: domain" -w /opt/Seclists/DNS/subdomains-top1million-110000.txt -t 150 -fw 20



BURP - intercept requests

Caido - intercept requests

Procurar por vulns web > [Broken link](/broken/pages/nRlZ9qImQSw2gTtp9WfL "mention")











Bruteforce hash&#x20;

hashcat --identify hash

hashcat -a0 -m3200 hash /usr/share/wordlists/rockyou.txt --show





descobrir backend&#x20;

../../../../../../../etc/passwd

