# Rustインストール手順


## aptのアップデート

最初にUbuntu標準のパッケージマネージャであるaptをアップデートします。  
絶対に必要な動作ではありませんが、、、 

```bash
# イロイロ最新に
sudo apt update
sudo apt upgrade
```


## Rust インストール

```bash
curl https://sh.rustup.rs -sSf | sh
# インストール設定はデフォルト(1)で!!!
# 次に環境変数(PATH)を設定します。

export PATH="$HOME/.cargo/bin:$PATH"

# 最後に正しくインストール、パスの設定がされたか、以下のコマンドで確認します。
cargo --version
# -> cargo 1.63.0
rustc 1.63.0
# -> rustc 1.63.0
rustdoc --version
# -> rustdoc 1.63.0
```
