##**ハニーポット構築**

AWSのUbuntu 16.04 LTSにcowrieをインストールします。

時刻変更

```markdown
$ sudo timedatectl set-timezone Asia/Tokyo
```

ポートを22から別ポートへ変更
```markdown
$ vi /etc/ssh/sshd_config
```

cowrieユーザ作成
```markdown
$ sudo adduser --disabled-password cowrie
```

リポジトリをクローン
```markdown
$ git clone http://github.com/micheloosterhof/cowrie
```

パッケージをインストール
```markdown
$ virtualenv cowrie-env
$ source cowrie-env/bin/activate
(cowrie-env) $ pip install -r requirements.txt
```

環境変数設定
```markdown
$ export PYTHONPATH=/home/cowrie/cowrie
```

22と23ポートへの通信をCowrieが待ち構えているポート2222と2223へリダイレクトする設定
```markdown
$ sudo iptables -t nat -A PREROUTING -p tcp --dport 22 -j REDIRECT --to-port 2222
$ sudo iptables -t nat -A PREROUTING -p tcp --dport 23 -j REDIRECT --to-port 2223
```

cowrie起動
```markdown
$ bin/cowrie start
```
