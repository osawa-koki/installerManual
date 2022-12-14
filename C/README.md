# C言語インストール手順

C言語のインストール手順は少し複雑です。  
正確にはC言語のコンパイラの取得自体は簡単ですが、パッケージマネージが存在しないため、環境構築が面倒くさいです、、、(´;ω;｀)  

まあ、かなり古い言語ですからね、、、  
我慢しましょう、、、  

## Cコンパイラの取得

C言語のコンパイラの名前はgccです。  
「GNU Compiler Collection」の略称です。  
システムレベルでC言語を使用する際には、ccコマンドで使用しますが、単にgccに対するリンクがはられているだけで、その実態はgccであることが大半です。  

練習用の環境であれば、gccのみをインストールすればok!ですが、一般的にはライブラリを結合・etc...って処理をする必要があり、これを実現するためにはgccだけでは困難です。  
したがって、オールインワンなコンパイラプログラム群をインストールする必要がありますが、これらは以下のコマンドでまとめて取得可能です。  

中身は[https://packages.ubuntu.com/focal/build-essential](https://packages.ubuntu.com/focal/build-essential)に記載されています。  

- dpkg-dev (>= 1.17.11)
- g++ (>= 4:9.2)
- gcc (>= 4:9.2)
- libc6-dev
- make

```bash
sudo apt install build-essential
```

これでgccとか、makeとかC言語でプログラムを作成する際に使用するモジュールをインストールできます。  
各構成要素が正しくインストールされたかは以下のコマンドで確認できます。  

```bash
gcc --version
c++ --version
make --version
```
