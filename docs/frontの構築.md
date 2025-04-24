# frontend開発環境の構築
## 概要
- React + Dockerの環境を作ります。

## 手順
1. reactアプリを構築
```
cd tools/react-init
docker compose build
docker compose run --rm -u "$(id -u):$(id -g)" app sh -c "npx create-react-app front"
mv front ../../
cd docker
cp docker-compose.yml Dockerfile ../../../front
```

## 参考
- https://www.docker.com/ja-jp/blog/how-to-dockerize-react-app/
- https://qiita.com/maooz4426/items/ec1b2694e2488ec3ebc2

