# myportal
## 環境構築(Windows11)
### 1. wslにubuntuを入れる(今回はNoble 24.04を利用)
[WSL を使用して Windows に Linux をインストールする方法](https://learn.microsoft.com/ja-jp/windows/wsl/install)
```
wsl --list --online
wsl --list
wsl --install Ubuntu-24.04
```

username, passwordをubuntuに設定後、
アップグレード
```
sudo apt update && sudo apt upgrade
```

### 2. docker engineを入れる
* [参考](https://docs.docker.com/engine/install/ubuntu/#install-from-a-package)

1. Dockerのaptリポジトリを設定する
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

2. Dockerパッケージをインストールする
```
sudo apt-get install docker-ce docker-ce-cli ontainerd.io docker-buildx-plugin docker-compose-plugin
```

3. 非ルートユーザーでもdockerが管理できるようにする
3.1 グループ作成
```
sudo groupadd docker
```

3.2 ユーザーをdockerグループに追加
```
sudo usermod -aG docker $USER
```

3.3 変更を有効にする
```
newgrp docker
```


### 3. Git＆GitHubの設定
1. Git for windowsのインストール
[ダウンロードサイト](https://gitforwindows.org/)


2. Gitの設定
```
git config --global user.name "xxxx"
git config --global user.email "xxx@xxx"
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/bin/git-credential-manager.exe"
```

### 4. Visual Studio Codeのインストールと設定
1. 下記よりダウンロードしてインストール
[Download Visual Studio Code](https://code.visualstudio.com/download)

2. 拡張機能パックをインストール
* Remote Development

3. wslからVS Codeを開く
```
code .
```

## 5. ソースダウンロード
1. git clone
```
git clone https://github.com/shn4pt/myportal.git
```










