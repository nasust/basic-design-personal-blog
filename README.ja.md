# Hugo Theme Basic Design Personal Blog

シンプルなブログのテーマです。
カスタマイズしやすいようにプレーンなデザインにしています。

## 特徴

- HTML5
- SCSS
- AMP
- レスポンシブデザイン
- グローバルメニュー
- 階層カテゴリ
- タグ
- アイキャッチ
- ページネーション

## インストール

```shell
$ cd themes
$ git clone git@github.com:nasust/basic-design-personal-blog.git
```

## 設定

### AMPのページを作成する

```toml
[outputs]
    page = [ "HTML" , "AMP"  ]
```

### プロフィール画像を指定します

```toml
[Params]
    profile_image = "images/avatar_image.jpg"
```

画像は``assets/images/avatar_image.jpg``に置きます。

### 名前を指定します

```toml
[Params]
    author = "Your Name"
```

### デフォルトのアイッキャッチ画像

```toml
[Params]
    eyecatch = "images/eyecache.jpg"
```

画像は``assets/images/eyecache.jpg``に置きます。

Markdownでアイッキャッチ画像の指定が無い場合の画像を指定します。

### おすすめのpermalinkフォーマット

```toml
[permalinks]
    post = "/:section/:year/:month/:filename"
```

デフォルトではサブセクションもパスに含まれる為、
記事を別のサブセクションに移動すると、URLが変わってしまいます。

### グローバルメニュー

```toml
[menu]
    [[menu.global_header]]
        name = "Home"
        url = "/"
        weight = 1
    [[menu.global_header]]
        name = "Blog"
        url = "/post"
        weight = 2
    [[menu.global_header]]
        name = "About"
        url = "/about"
        weight = 3
```

### 例

```toml
baseURL = "http://example.org/"
title = "Basic Design Personal Blog"
defaultContentLanguage = "ja"
languageCode = "ja-jp"
disablePathToLower = true
hasCJKLanguage = true
pluralizeListTitles = false
pygmentsUseClasses = true
pygmentsCodefences = true
theme = "basic-design-personal-blog"

[outputs]
    page = [ "HTML" , "AMP"  ]

[Params]
    author = "Hoge"
    profile_image = "images/profile.jpg"
    eyecatch = "images/eyecache.jpg"

[taxonomies]
    tag = "tags"

[permalinks]
    post = "/:section/:year/:month/:filename"

[blackfriday]
    hrefTargetBlank = true
    nofollowLinks = true
    extensionsmask = ["autolink"]

[menu]
    [[menu.global_header]]
        name = "Home"
        url = "/"
        weight = 1
    [[menu.global_header]]
        name = "Blog"
        url = "/post"
        weight = 2
    [[menu.global_header]]
        name = "About"
        url = "/about"
        weight = 3
```

## 階層カテゴリーについて

```bash
content
└── post
    ├── general --------------- カテゴリー
    ├── cateogry_1 ------------ カテゴリー
    │   ├── sub_category_1 --- サブカテゴリー
    │   └── sub_category_2 --- サブカテゴリー
    └── cateogry_2  ----------- カテゴリー
```

階層カテゴリーをサポートしています。
サブセクションがカテゴリーとして扱われます。
サブセクションの更に下のセクションはサブカテゴリーとして扱われます。

## Markdown Front Matter

### eyecache

```yaml
eyecache: "eyecache.jpg"
```

アイキャッチ画像を設定します。

以下の通りで画像を検索して表示します。

1. ページリソース
2. assetディレクトリ

### tags

```yaml
tags: ["tag 1" , "tag 2"]
```

タグを設定します。

### 例

```yaml
title: "ブログタイトル"
date: 2019-06-17
draft: false
eyecache: "eyecache.jpg"
tags: ["雑記" , "ポエム" ]
```





