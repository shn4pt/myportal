# api-phpの構築
1. 最新のLaravelをインストール
```
curl -s "https://laravel.build/example-app" | bash
```

2. ComposerのDockerイメージを利用してSailを含むComposerの依存パッケージをインストール
　1の手順で、依存関係含めてインストールされるが、gitにコミットする際は、依存関係はpushされないので、
　他の開発者がpullした後に実施が必要
```
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php84-composer:latest \
    composer install --ignore-platform-reqs
```

