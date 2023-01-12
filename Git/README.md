# Gitインストール手順

Linuxには原則としてGitがプリインストールされているため、インストールを行う必要はありません。  
以下のコマンドは、特殊なカスタマイズがされたディストリビューション向けです。  

以下の方法では少し古いバージョンのGitプログラムがインストールされます。  
最新のバージョンのGitを使用したい場合には、「# Gitのアップデート」へ進んでください。  

```bash
sudo apt-get install git-all
```

自身のコンピュータにGitがインストールされているかは以下のコマンドで確認できます。  

```bash
git --version

# -> git version 2.25.1
```

## Gitのアップデート

デフォルトでインストールされている、ないしはyumやaptといったOS標準のパッケージマネージャでインストールされるGitは少し古いことが多いです。  
最新のGitを使いたいという方はソースコードを取得してコンパイルして生成する方法が一般的です。  

Gitの最新バージョンは「[https://git-scm.com/](https://git-scm.com/)」から確認できます。  

詳しい説明は[https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)から取得して下さい。  

```bash
# 古いバージョンのGitをアンインストール
sudo apt -y remove git

# コンパイルに必要な機能のインストール
sudo apt-get install libcurl4-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev

# ドキュメント出力に必要な機能のインストール
sudo apt-get install asciidoc xmlto docbook2x
# -> E: Unable to locate package asciidoc
# -> E: Unable to locate package xmlto
# -> E: Unable to locate package docbook2x
# エラー、、、(´;ω;｀)
# この場合はaptのアップデートで大抵は解決できます♪

# aptのアップデート
sudo apt update
# ついでに、、、
sudo apt upgrade

# もう一回チャレンジ!!!
sudo apt-get install asciidoc xmlto docbook2x
# おそらく実行されるハズ、、、
```

これで、ソースコードをコンパイルする環境が整いました♪  
次にソースコードをダウンロードしましょう♪  

以下のサイトから取得できます。  

- <https://mirrors.edge.kernel.org/pub/software/scm/git/>
- <https://github.com/git/git/releases>

今回は[https://mirrors.edge.kernel.org/pub/software/scm/git/](https://mirrors.edge.kernel.org/pub/software/scm/git/)からダウンロードしましょう♪  

最新の「*****.tar.gz」ファイルをダウンロードしてください。  
「htmldocs」や「manpages」をダウンロードしないように注意して下さい。  

```bash
# ソースコードをダウンロードして
wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-*****.tar.gz

# 解凍します。
tar zxvf git-*****.tar.gz
```

```bash
# コンパイル時に足りないモジュールを発見したのでインストール
sudo apt install cc
sudo apt install autoconf
```

```bash
# ダウンロードしたディレクトリに移動して、、、
cd git-***
make configure
./configure --prefix=/usr
make all doc info
sudo make install install-doc install-html install-info
```

## Git初期設定

では、Gitの初期設定を行いましょう♪  

```bash
# ユーザ名・メールアドレスの登録
git config --global user.name "ユーザ名"
git config --global user.email "メールアドレス"

# デフォルトブランチの設定 (通常は「main」)
git config --global init.defaultBranch デフォルトブランチ名
```
