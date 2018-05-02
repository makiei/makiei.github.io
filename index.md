## ハニーポット観察記

AWS上に公開しているサーバにハニーポット(cowrie)をインストールし、どういうアクションが起きるかを観察します。

4/30～現在

### ログ

```markdown


"eventid": "cowrie.login.failed",
"username": "django", 
"timestamp": "2018-05-02T02:17:04.234366Z", 
"message": "login attempt [django/django] failed",
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,***,***.***.**.**", 
"isError": 0, 
"src_ip":  "***.***.***.**",
"session": "4bf5946999a6", 
"password": "django", 
"sensor": "ip-***-**-**-**"
```

```markdown
"eventid": "cowrie.login.failed",
"username": "support", 
"timestamp": "2018-05-02T02:23:42.249868Z", 
"message": "login attempt [support/support@123] failed", 
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,***,***.***.**.***", 
"isError": 0, 
"src_ip": "***.***.**.***", 
"session": "3d565634e758", 
"password": "support@123", 
"sensor": "ip-***-**-**-**"
```

```markdown
"eventid": "cowrie.login.failed", 
"username": "test9", 
"timestamp": "2018-05-02T02:25:01.762783Z", 
"message": "login attempt [test9/test9] failed", 
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,***,***.**.***.*", 
"isError": 0, 
"src_ip": "***.**.***.*", 
"session": "bc0952a4c85a", 
"password": "test9", 
"sensor": "ip-***-**-**-**"
```
