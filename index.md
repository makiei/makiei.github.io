## ハニーポット観察記

AWS上に公開しているサーバにハニーポット(cowrie)をインストールし、どういうアクションが起きるかを観察します。

4/30～現在

### ログ

```markdown


"eventid": "cowrie.login.failed",
"username": "django", 
"timestamp": "2018-05-02T02:17:04.234366Z", 
"message": "login attempt [django/django] failed",
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,263,115.159.105.14", 
"isError": 0, 
"src_ip":  "115.159.105.14",
"session": "4bf5946999a6", 
"password": "django", 
"sensor": "ip-172-31-46-78"
```

