# Dockerインストール手順

Docker公式サイトでインストール用のシェルスクリプトが用意されているため、これを実行します。

```bash
curl -fsSL https://get.docker.com/ | sh
```

インストールが正常に完了したかどうかは以下のコマンドで確認可能です。


```bash
docker --version
# -> Docker version 20.10.18, build b40c2f6
```

```bash
# 自動起動をオンに
sudo systemctl enable docker

# Dockerを起動
sudo systemctl start docker

# Dockerの状態を確認
systemctl status docker
```


# 参考文献

- [Docker公式ドキュメント](https://docs.docker.jp/engine/installation/linux/ubuntulinux.html)

