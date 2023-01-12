# .NETのインストール手順

「.NET Framework」でも「.NET Core」でもない純粋な「.NET」をインストール。  
もはやプラットフォームの考慮など不要です。  

## 20.*

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb

sudo apt-get update
sudo apt-get install -y dotnet-sdk-6.0
```

## 22.*

簡単になった。  

```bash
sudo apt-get update
sudo apt-get install -y dotnet-sdk-6.0
```

## SQL Serverのインストール手順

### 20.\*

Ubuntu 22.4.*系だと正常にインストールできません。

```bash
sudo apt-get install wget

wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

sudo apt-get install software-properties-common

sudo add-apt-repository "$(wget -qO- https://packages.microsoft.com/config/ubuntu/20.04/mssql-server-preview.list)"

sudo apt-get update
sudo apt-get install -y mssql-server
```

```bash
sudo /opt/mssql/bin/mssql-conf setup

# -> 3 (Express)
# -> simplequizapi_pw1234

systemctl status mssql-server --no-pager
```

### 22.\*

現段階だとインストールできない???  

## 参考資料

- [Ubuntuに.NETをインストールする方法](https://learn.microsoft.com/ja-jp/dotnet/core/install/linux-ubuntu)
- [.NETアプリケーションの実行](https://learn.microsoft.com/ja-jp/troubleshoot/developer/webapps/aspnetcore/practice-troubleshoot-linux/2-1-create-configure-aspnet-core-applications)
- [SQL Serverのインストール](https://learn.microsoft.com/ja-jp/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-ver16)
