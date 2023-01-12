# Rustインストール手順

## aptのアップデート

最初にUbuntu標準のパッケージマネージャであるaptをアップデートします。  
絶対に必要な動作ではありませんが、、、  

```bash
# イロイロ最新に
sudo apt update
sudo apt upgrade
```

## Rustに必要なモジュールのインストール

RustではC言語のコンパイラやその他もろもろの機能が必要ですので、それをインストールします。  
それっぽいツールは「build-essential」にまとめられているため、それをインストールします。  

```bash
sudo apt install build-essential
```

C言語コンパイラだけでイイって方はそれだけインストールして下さい。  
これだけでもRustを実行することは可能です。  

```bash
sudo apt install gcc
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
