# 技書博2ガイドブック

## 概要説明
公式ガイドブックの２のリポジトリです。

## この本の目的

事務局原稿とスポンサー記事をここで書きます。
えるきちさん開発の[easybook](https://github.com/erukiti/easybooks)に対応したので、mdのままでも行けるはず。

がんばって、10月中には事務局原稿を書き上げましょう。

## 執筆にあたってのお願い
app-dev.jsonの後半に、原稿ファイルを指定してください。

    "CHAPS": [
      "chap-easybooks.md",
      "chap-placeholder.md",
      "chap-software-design.md",
      "chap-ui-design.md"
      ここに追加。カンマ（,）で区切ってね。
    ],

画像は、chap-easybooksのように、原稿ファイル名でフォルダを作って、そこに格納。

CIでコンパイルが通ることを確認してください。エラーのまま放置はなるべくやめてください。

Confrictが発生した場合は、解決お願いします。

push -f等はやめましょう。（歴史を書き換えてはいけません。

相談事：
Issue立ててください。

## Re:VIEWの書き方

[Re:VIEWチートシート](https://gist.github.com/erukiti/c4e3189dda179a0f0b73299fb5787838) を作ってみたので、参考にしてみてください。

## CI
https://app.wercker.com/oyakata2438/Guidebook2/runs
でPDFが書きだされます。
一番上のBuildをクリックすると展開されるので、
Output Artifactをクリックして、Download artifactをクリックすると、
tarで固めたpdfがダウンロードできます。

## インストール

細かい準備(TeX入れたり)は[『技術書をかこう！』](https://github.com/TechBooster/C89-FirstStepReVIEW-v2)に準じます。

### WindowsでReviewを使う方法

https://qiita.com/implicit_none/items/398c6e0bbedc8b160621
暗黙の型宣言さんが詳しく書いてくれてます。あるいは、技術同人誌を書こう‐アウトプットのススメ‐をご覧ください。

### Dockerを使う方法

Dockerを使うのが一番手軽です。

```sh
$ docker run --rm -v `pwd`:/work vvakame/review /bin/sh -c "cd /work/articles ; review-pdfmaker config.yml"
```

### Docker使わずビルド

```sh
$ npm install; npm run build
```

### 権利

ベースには、[TechBooster/ReVIEW\-Template: TechBoosterで利用しているRe:VIEWのテンプレート（B5/A5/電子書籍）](https://github.com/TechBooster/ReVIEW-Template) を使っています。

  * 設定ファイル、テンプレートなど制作環境（techbooster-doujin.styなど）はMITライセンスです
    * 再配布などMITライセンスで定める範囲で権利者表記をおねがいします
