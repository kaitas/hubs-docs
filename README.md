# Mozilla Hubs 日本語版ドキュメント

ここは [Mozilla Hubs](http://hubs.mozilla.com) と Hubs Cloud や Spoke などの関連プロダクトのための日本語版ドキュメントのためのリポジトリです。

このドキュメントは（[本家](https://github.com/MozillaReality/hubs-docs)がそうであるように）、まだ活動的に開発中です。
もしみなさんが変更すべき点や更新すべき点を発見したら、プルリクエストや公式の [Discord Server](http://discord.gg/wHmY4nd) でお伝えください。

（訳者自体は Mozillaの人ではありませんので、日本語でお急ぎの場合は [Twitter@o_ob](https://twitter.com/o_ob)でお伝えください）

このウェブサイトは [Docusaurus](https://docusaurus.io/) で作られています。

This repo is for Japanese documentation for [Mozilla Hubs](http://hubs.mozilla.com), and related products such as Hubs Cloud and Spoke. 
(Contact me via [Twitter@o_ob](https://twitter.com/o_ob), if you need to communicate me as soon as possible.)


# Docusaurus についての情報
## このドキュメントについて

* [5分ではじめるDocusaurus](#5分ではじめるDocusaurus)
* [ディレクトリ構造](#ディレクトリ構造)
* [コンテンツの編集](#コンテンツの編集)
* [コンテンツの追加](#コンテンツの追加)
* [より詳細な情報](#より詳細な情報)

## 5分ではじめるDocusaurus

1. ウェブサイト構築のための依存関係がすべてインストールされていることを確認します：

```sh
# website directory ディレクトリに移動
$ cd website

# 依存関係のインストール
$ yarn
```
2. 開発サーバを起動:

```sh
# サイトを起動します
$ yarn start
```

訳注：WindowsのVistual Studio Codeの環境で yarn がインストールされず、Chocolateyがインストールされている場合、PowerShellを管理者モードで起動して ` choco install yarn` で yarn をインストールできます。くわしくは[こちら](https://classic.yarnpkg.com/en/docs/install#windows-stable)

### ディレクトリ構造

プロジェクトファイルの構造は以下のようにしてください

```
my-docusaurus/
  docs/
    doc-1.md
    doc-2.md
    doc-3.md
  website/
    core/
    node_modules/
    pages/
    static/
      css/
      img/
    package.json
    sidebar.json
    siteConfig.js
```

## コンテンツの編集

### 既に存在する docs ページ

`docs/` 以下を探して、関連するドキュメントを編集してください：

`docs/doc-to-be-edited.md`

```markdown
---
id: page-needs-edit
title: 編集されるドキュメントのタイトル
---

以下、本文...
```

ドキュメントについてのより詳しい情報は、[こちら](https://docusaurus.io/docs/en/navigation)を参照してください。

### 既存のブログ投稿を編集する

`website/blog` 以下を探して、関連する投稿を編集してください：


`website/blog/post-to-be-edited.md`
```markdown
---
id: post-needs-edit
title: 編集されるブログのタイトル
---

以下、本文...
```

ブログ投稿についての詳細は、 [こちら](https://docusaurus.io/docs/en/adding-blog)を参照。

## コンテンツの追加

### 既に存在するサイドバーに新しいドキュメントを追加

1. `/docs` 以下に， `docs/newly-created-doc.md` という形式で markdown形式の新規ドキュメントを追加：


```md
---
id: newly-created-doc
title: （新規作成したドキュメントのタイトル）
---

新規作成した内容を以下..
```

1. `website/sidebar.json` のサイドバー項目において、上記のドキュメントIDを追記：

```javascript
// ドキュメントの入門(Getting Started)カテゴリに新しく作成したドキュメントを追加
{
  "docs": {
    "Getting Started": [
      "quick-start",
      "newly-created-doc" // 新規作成したドキュメントがこれ
    ],
    ...
  },
  ...
}
```

新規ドキュメント作成についてのより詳しい情報は、[こちら](https://docusaurus.io/docs/en/navigation)をご参照ください。

## より詳細な情報

docusaurus についてのドキュメント全文は [website](https://docusaurus.io/) をご参照ください。
