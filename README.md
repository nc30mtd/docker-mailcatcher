# docker版 MailCatcher

## 事前作業
dockerとdokcer-composeのインストールが必要なので事前にインストールを行ってください

## コンテナの起動

```
cd docker-mailcatcher
docker-compose up -d
```


## コンテナの停止

```
cd docker-mailcatcher
docker-compose down
```

## ホスト-コンテナ間のポート紐付け設定

コンテナ上でMailCatcherは1025と1080のポートを利用してサービスを実行しています．

```
#Dockerfile L.14

EXPOSE 1025 1080
```


ホスト上のポートとコンテナ上のポートの紐付けはdocker-compose.ymlで定義しています
下記の例ではコンテナ上の1080をホスト上の8080に，コンテナ上1025をホスト上の8081に割付しています

```
    ports:
      - 8080:1080
      - 8081:1025
```


