# リバースプロキシの練習

## ディレクトリ構成
```
├── README.md
├── app
│   ├── docker-compose.yml
│   └── html
│       └── index.html
└── reverse-proxy
    ├── docker-compose.yml
    └── nginx.conf
```

## 実装の概要
localhost:8080にアクセスするとappのindex.htmlが表示される。  
localhost:80リバースプロキシ用のnginxにでアクセスされ、そこからlocalhost:8080に移るので、appのindex.hmlが表示される。

## nginx.confの注意点
- host.docker.internalは、Docker Desktopの内部DNSの一部として機能するため、Docker Desktop以外の環境では使用できない。
- host.docker.internalは、macOSおよびWindows上のDocker Desktopでのみサポートされている。
- Dockerのバージョンが18.03以上である必要がある。
- Linux環境ではhost.docker.internalが直接サポートされていないため、代わりにホストマシンのIPアドレスを明示的に指定する必要がある。
