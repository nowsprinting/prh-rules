# A collection of prh rules

[![Test](https://github.com/nowsprinting/prh-rules/actions/workflows/test.yml/badge.svg)](https://github.com/nowsprinting/prh-rules/actions/workflows/test.yml)


## upstreamとの差分

以下のルールを追加しています

* media
    * ikagoya.yml（techbooster.ymlをベースに、下記termsに追加したファイルをインポートしています）
* terms
    * csharp.yml
    * istqb_ja.yml
    * jetbrains.yml
    * unity.yml
    * xutp.yml


## 推奨allow.yml

[textlint-filter-rule-allowlist](https://github.com/textlint/textlint-filter-rule-allowlist)を使用して、次のワードを無視するよう設定することを推奨します。

```
- /https?://[\w!\?/\+\-_~=;\.,\*&@#\$%\(\)'\[\]]+/  # URL内はcase sensitiveにしない
- パラメタライズドテスト  # /パラメーター?/に抵触してしまうため

# ファイル名の拡張子として小文字表記を認める
- .html
- .json
- .unity
```

## フォルダ構成

* languages
    * 各自然言語固有のルール
* terms
    * 技術用語のルール
    * 商標やツールの正式名称などのルール
    * 各種ツール固有のルール
* media
    * 各媒体固有のルール
* files
    * 各ファイルタイプ毎のinclude, excludeの設定


## ルール

* yaml内でimportを使ってはならない
    * rootディレクトリのprh.ymlとmediumの中は除く
* 原則として、media内のルールを他のファイルから参照しない（組み合わせて運用する前提のものではないため）
* mediaには原則として、各団体・出版社別ルールを置く
    * 作品別ルールは作品のリポジトリにて個別に管理するのを推奨する
* 団体内部で複数のファイルを置きたい場合、 media/techbooster/ のように団体名のディレクトリを切ってその中で自由にすること
