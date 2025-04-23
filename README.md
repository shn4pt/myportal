# myportal
## 環境構築(Windows11)
### 1. wslにubuntu Noble 24.04(LTS)を入れる
* [参考](https://learn.microsoft.com/ja-jp/windows/wsl/install#manual-installation-steps)
```
wsl --list --online
wsl --list
wsl --install Ubuntu-24.04
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




