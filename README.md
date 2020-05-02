# Mozilla Hubs Docs 日本語版

ここは [Mozilla Hubs](http://hubs.mozilla.com) と Hubs Cloud や Spoke などの関連プロダクトのための日本語版ドキュメントのためのリポジトリです。

このドキュメントは（本家がそうであるように）、まだ活動的に開発中です。
もしみなさんが変更すべき点や更新すべき点を発見したら、プルリクエストや公式の [Discord Server](http://discord.gg/wHmY4nd) でお伝えください。

（訳者自体は Mozillaの人ではありませんので、日本語でお急ぎの場合は [Twitter@o_ob](https://twitter.com/o_ob)でお伝えください）

このウェブサイトは [Docusaurus](https://docusaurus.io/) で作られています。

This repo is for Japanese documentation for [Mozilla Hubs](http://hubs.mozilla.com), and related products such as Hubs Cloud and Spoke. 
(Contact me via [Twitter@o_ob](https://twitter.com/o_ob), if you need to communicate me as soon as possible.)


# Docusaurus information 
## What's In This Document

* [Get Started in 5 Minutes](#get-started-in-5-minutes)
* [Directory Structure](#directory-structure)
* [Editing Content](#editing-content)
* [Adding Content](#adding-content)
* [Full Documentation](#full-documentation)

## Get Started in 5 Minutes

1. Make sure all the dependencies for the website are installed:

```sh
# Navigate to the website directory
$ cd website

# Install dependencies
$ yarn
```
2. Run your dev server:

```sh
# Start the site
$ yarn start
```

### Directory Structure

Your project file structure should look something like this

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

## Editing Content

### Editing an existing docs page

Edit docs by navigating to `docs/` and editing the corresponding document:

`docs/doc-to-be-edited.md`

```markdown
---
id: page-needs-edit
title: This Doc Needs To Be Edited
---

Edit me...
```

For more information about docs, click [here](https://docusaurus.io/docs/en/navigation)

### Editing an existing blog post

Edit blog posts by navigating to `website/blog` and editing the corresponding post:

`website/blog/post-to-be-edited.md`
```markdown
---
id: post-needs-edit
title: This Blog Post Needs To Be Edited
---

Edit me...
```

For more information about blog posts, click [here](https://docusaurus.io/docs/en/adding-blog)

## Adding Content

### Adding a new docs page to an existing sidebar

1. Create the doc as a new markdown file in `/docs`, example `docs/newly-created-doc.md`:

```md
---
id: newly-created-doc
title: This Doc Needs To Be Edited
---

My new content here..
```

1. Refer to that doc's ID in an existing sidebar in `website/sidebar.json`:

```javascript
// Add newly-created-doc to the Getting Started category of docs
{
  "docs": {
    "Getting Started": [
      "quick-start",
      "newly-created-doc" // new doc here
    ],
    ...
  },
  ...
}
```

For more information about adding new docs, click [here](https://docusaurus.io/docs/en/navigation)

## Full Documentation

Full documentation can be found on the [website](https://docusaurus.io/).
