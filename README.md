# setup
VScode、Git、GitHub、Ubuntuを使用した開発ができるよう、セットアップを行いましょう。


## Ubuntu（Linux）
ホストOSを汚さないようゲストOSを用意します。  
Linuxは開発する上で安定しており、様々なツールが用意できるので大変便利です。  
これを機会にLinuxを扱えるようになりましょう。  
(インストールに時間がかかるのでこれから始めます)  
### Windows
1. WSL2を有効化する
起動する前にWSL2を有効化しておく必要があります。  
※再起動が必要になります。  
（参考）https://www.kagoya.jp/howto/it-glossary/develop/wsl2_linux/  
    1. Linuxインストール前の準備を行う  
    1. WSL2用Linuxカーネルをインストールする  
    1. WSL2を既定のバージョンで利用できるようにする  

2. MicrosoftStoreを起動する  
![MicrosoftStore](Images/MicrosoftStore.png)

3. Ubuntuで検索する  
Ubuntu 22.04.2 LTS が安定していて、利用者が多いです。
![Ubuntu](Images/Ubuntu_Install.png)

4. 起動する  
ユーザー名、パスワードを決めるよう促される。  
※必ず入力する。うっかり画面を閉じてしまわないよう注意。  
※初回起動はセットアップに時間がかかります。（5分程度？）  
![Ubuntu](Images/Ubuntu2204-01.png)

5. UbuntuのVesionを確認する  
```bash  
lsb_release -a
```  


### Mac
Ubuntu入れる必要は無い説あり。調査中。


## GitHub
1. サインアップ  
以下のページへアクセスしてアカウントを作成します。  
詳しいことは別のサイトを参照しながら進めてください。  
　（参考）https://qiita.com/ayatokura/items/9eabb7ae20752e6dc79d

```bash
https://github.com/
```

2. サインイン  
サインインに成功するか確認します。  

3. トークンの発行  
リポジトリのクローンやプッシュなど、あらゆる場面でトークンの入力を求められます。  
トークンは再発行できますが、面倒なので無くさないように管理します。  
※詳しいことは別のサイトを参照しながら進めてください。  
　（参考）https://capybara-notebook.com/github_accesstoken/


## Git（Ubuntuへインストール）
リポジトリをクローンするなどの操作に使用します。
ホストOSでは使用しないのでUbuntuに入れます。
1. インストール  
まずはUbuntu上で以下のコマンドを打ってみます。
Versionが返ってきたらすでにインストールされています。
```bash
git version
```
- もし、インストールされていなければ、Ubuntu上でこのコマンドを実行するだけ。  
とても簡単。  
(念のため、実行しておいても良い)   

```bash
sudo apt update
sudo apt-get install git
```

2. 初期設定  
[GitHub](#github)で作成したアカウントを登録します。  
```bash
git config --global user.name "yamada-taro"
git config --global user.email xxx@yahoo.co.jp
```

## VSCode(ホストOSへインストール)
様々な拡張機能が備わっており、これひとつで開発可能な統合開発環境です。  
1. インストール  
以下からインストーラを取得します。  
インストールを実施。
```bash
https://code.visualstudio.com/
```
2. VScodeを起動して拡張機能を導入
- Japanese Language Pack for Visual Studio Code
- Remote-WSL
- Git Graph
- Git History
- Dev Containers
- Docker
- Bazel
- Draw.io Integration

## Docker
ここまで行けるかわからないので放置  

## Jenkins
1. WSL2(Ubuntu)側で以下のコマンドを順番に実行
```
$ sudo apt -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
# JAVA
$ sudo apt -y install openjdk-8-jdk
$ sudo apt -y install openjdk-11-jre-headless
# Jenkins
$ wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add
$ sudo bash -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
$ sudo apt update
$ sudo apt install jenkins
# Update Firewall to enable Jenkins service
$ sudo ufw enable
$ sudo ufw allow 8080 # whatever port number you like
$ Check the status of your port:
$ sudo ufw status
# Run Jenkins server
$ sudo service jenkins start
# この後、Winodwsブラウザのhttp://localhost:8080/ からJenkinsにアクセスできる
# できない場合は JenkinsにWSLをpower shellから`wsl.exe --shutdown` で再起動してから再度jenkins startしてみる
# 初期パスワード確認
$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
- 以下の画面が出ればOK  
![MicrosoftStore](Images/Jenkins_first.png)
- 上記に初期パスワードを入力する  

2. 次にプラグインのインストール確認画面が表示される。  
「Install suggested plugins」を選択する。

3. 自動的にプラグインのダウンロード＆インストールが始まるのでインストールが完了するまで待つ。  

4. 初期Adminユーザ作成画面が表示されるので必要事項を入力して[Save and Continue]ボタンを押す。  

# supplement
## ブランチを保護したい  
mainブランチへ直接Pushできないように保護する方法  
https://zenn.dev/snowcait/articles/42bb6b56c806da



