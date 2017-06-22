# ともえ会 C92

ともえ会のC92用リポジトリです。

## 構成

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
