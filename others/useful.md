---
description: useful things
---

# Useful

**Ajustar teclado para padrão brasileiro:**\
`setxkbmap -model abnt2 -layout br -variant abnt2`

**Compilar em 32 bits**\
`apt-get install gcc-multilib g++-multilib`

**Fechar negociacao com criptografia mais baixa caso necessário**\
`vi /etc/ssh/ssh_config`

**Adicionar a linha abaixo**\
`KexAlgorithms curve25519-sha256,curve25519-sha256@libssh.org,ecdh-sha2-nistp256,ecdh-sha2-nistp384,ecdh-sha2-nistp521,diffie-hellman-group-exchange-sha256,diffie-hellman-group16-sha512,diffie-hellman-group18-sha512,diffie-hellman-group14-sha256,diffie-hellman-group-exchange-sha1`

**Registrar a apitoken do wpscan**\
a) https://wpscan.com/register\
b) guardar o token\
c) passar de parametro\
`wpscan --url http://site.com/wordpres --api-token xxxxx`

**Levantar um servidor web com python**\
`python3 -m http.server 80`

**Atualizar o RubyGems**\
`gem update --system`

**Python TTY**\
`python -c 'import pty;pty.spawn("/bin/bash");'`

**Lista dos comandos que o usuário tem permissão para executar como root:**\
`sudo -l`

**Escalação de privilegios com searchsploit**\
`searchsploit linux local ubuntu 14.04`

**Kernel**\
`uname -a`

\
**Para montar um Simple FTP Server com Python:**\
[http://pythonclub.com.br/pyftpdlib-criando-um-servidor-ftp-simples-com-python.html](http://pythonclub.com.br/pyftpdlib-criando-um-servidor-ftp-simples-com-python.html)<br>

**Foto de pessoas que não existem + IA** \
[https://thispersondoesnotexist.com/](https://thispersondoesnotexist.com/)
