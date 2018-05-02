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

```markdown
"eventid": "cowrie.login.failed",
"username": "support", 
"timestamp": "2018-05-02T02:23:42.249868Z", 
"message": "login attempt [support/support@123] failed", 
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,265,134.117.78.100", 
"isError": 0, 
"src_ip": "134.117.78.100", 
"session": "3d565634e758", 
"password": "support@123", 
"sensor": "ip-172-31-46-78"
```
