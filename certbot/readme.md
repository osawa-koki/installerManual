# Let's Encrypt


無料で使用できる「Let's Encrypt」を使用します。

```bash
sudo apt install certbot
sudo certbot certonly --standalone -d ドメイン名
```

更新は以下の手順で♪

```bash
# 80番ポートを解放
lsof -i -P
kill -9 プロセス

sudo certbot renew
```

