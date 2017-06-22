# ともえ会 C92

ともえ会のC92用リポジトリです。

## 構成

Re:VIEWやその他の環境は全て[Docker](https://www.docker.com/)上で構築されています。
そのため事前にDockerのインストールが必要です。

またこれから説明することについては、全て `tomoekai/c92` リポジトリのルートディレクトリ上で実行されているものとします。
次の説明を読む前に `pwd` と実行して `tomoekai/c92` 上にいることを確認してください。

## Dockerイメージのビルド

本をビルドしたり誤字脱字を確認するのにDockerが必要です。
またDockerのイメージ化はされていないので、はじめに次のコマンドを実行する必要があります。
これを実行するとき、初回は2GBほどのデータをダウンロードしてくるので通信環境には気をつけてください。

`docker build -t review-preview .`

## テスト

原稿に誤字脱字やよくない表現が無いか確認をおこなうために[RedPen](http://redpen.cc/)を使っています。
RedPenを実行するには次のコマンドを実行します。

```
docker run --rm -v `pwd`:/work review-preview /bin/sh -c "/usr/local/bin/redpen /work/articles/*.re"`
```
