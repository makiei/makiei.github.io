## ハニーポット観察記

AWS上に公開しているサーバにハニーポット(cowrie)をインストールし、どういうアクションが起きるかを観察します。

4/30～現在

### ログ
（IPアドレスは伏せ）

```markdown


"eventid": "cowrie.login.failed",
"username": "django", 
"timestamp": "2018-05-02T02:17:04.234366Z", 
"message": "login attempt [django/django] failed",
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○○.○○", 
"isError": 0, 
"src_ip":  "○○○.○○○.○○○.○○○",
"session": "4bf5946999a6", 
"password": "django", 
"sensor": "ip-○○○-○○○-○○○-○○○"
```

```markdown
"eventid": "cowrie.login.failed",
"username": "support", 
"timestamp": "2018-05-02T02:23:42.249868Z", 
"message": "login attempt [support/support@123] failed", 
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○○.○○", 
"isError": 0, 
"src_ip": "○○○.○○○.○○○.○○○",
"session": "3d565634e758", 
"password": "support@123", 
"sensor": "ip-○○○-○○○-○○○-○○○"
```

```markdown
"eventid": "cowrie.login.failed", 
"username": "test9", 
"timestamp": "2018-05-02T02:25:01.762783Z", 
"message": "login attempt [test9/test9] failed", 
"system": "SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○○.○○", 
"isError": 0, 
"src_ip": "○○○.○○○.○○○.○○○", 
"session": "bc0952a4c85a", 
"password": "test9", 
"sensor": "ip-○○○-○○○-○○○-○○○"
```
5/3～
```markdown
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] connection lost
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] Connection lost after 3 seconds
[cowrie.ssh.factory.CowrieSSHFactory] New connection: ○○○,○○○.○○○.○.○○○:57710 (○○○,○○○.○○○.○.○○○) [session: 6e4cd0125d02]
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] connection lost
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] Connection lost after 0 seconds
[cowrie.ssh.factory.CowrieSSHFactory] New connection: ○○.○○.○○○.○○○:45160 (○○○,○○○.○○○.○.○○○) [session: ce591eea566c]
[cowrie.ssh.factory.CowrieSSHFactory] New connection: ○○.○○.○○○.○○○:45164 (○○○,○○○.○○○.○.○○○) [session: e73deaa4c0b2]
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] Remote SSH version: SSH-2.0-OpenSSH_6.7p1 Raspbian-5+deb8u4
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] kex alg, key alg: 'ecdh-sha2-nistp256' 'ssh-rsa'
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] outgoing: 'aes128-ctr' 'hmac-sha1' 'none'
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] incoming: 'aes128-ctr' 'hmac-sha1' 'none'
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] Remote SSH version: SSH-2.0-OpenSSH_6.7p1 Raspbian-5+deb8u4
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] kex alg, key alg: 'ecdh-sha2-nistp256' 'ssh-rsa'
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] outgoing: 'aes128-ctr' 'hmac-sha1' 'none'
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] incoming: 'aes128-ctr' 'hmac-sha1' 'none'
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] NEW KEYS
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] NEW KEYS
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] starting service 'ssh-userauth'
[HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] starting service 'ssh-userauth'
[SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] 'pi' trying auth 'none'
[SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] 'pi' trying auth 'none'
[SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] 'pi' trying auth 'password'
[SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] login attempt [pi/raspberryraspberry993311] failed
[SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] 'pi' trying auth 'password'
[SSHService 'ssh-userauth' on HoneyPotSSHTransport,○○○,○○○.○○○.○.○○○] login attempt [pi/raspberry] failed
```

RaspberryPiを標的にした攻撃も来はじめました。

5/7～
```markdown
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:07.463310Z", "message": "login attempt [RPM/<Any pass>] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:08.534857Z", "message": "login attempt [RPM/RPM] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:09.606393Z", "message": "login attempt [RPM/admin] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:10.678061Z", "message": "login attempt [RPM/sftp] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:11.749492Z", "message": "login attempt [RPM/Pass1234] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:12.820923Z", "message": "login attempt [RPM/P@ssw0rd] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:13.892404Z", "message": "login attempt [RPM/root] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:16.048359Z", "message": "login attempt [RPM/test] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:17.119649Z", "message": "login attempt [RPM/1234]  
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:18.191143Z", "message": "login attempt [RPM/ubnt] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:19.262464Z", "message": "login attempt [RPM/monitor] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:20.334143Z", "message": "login attempt [RPM/scanner] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:21.405489Z", "message": "login attempt [RPM/support] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:22.477047Z", "message": "login attempt [RPM/12345] 
"eventid": "cowrie.login.failed", "username": "RPM", "timestamp": "2018-05-08T13:26:23.553110Z", "message": "login attempt [RPM/PlcmSpIp] 
```
総当りも増えてきました。
そろそろログ可視化に着手します。
