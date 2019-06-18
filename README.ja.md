# Basic Design Personal Blog
Hugo Theme Basic Design Personal Blog

シンプルなブログのテーマです。
カスタマイズしやすいようにプレーンなデザインにしています。

## Features

- HTML5
- SCSS
- AMP
- レスポンスデザイン
- 階層カテゴリ
- タグ
- アイキャッチ
- グローバルメニュー

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
    profile_image = ""
```

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

Markdownでアイッキャッチ画像の指定が無い場合の画像を指定します。

### おすすめのpermalinkフォーマット

```
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

## 例: config.toml

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
    profile_image = ""
    author = "Hoge"
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
Your Site
└── post
    ├── general
    ├── cateogry_1
    │   ├── sub_category_1
    │   └── sub_category_2
    └── cateogry_2
```

階層カテゴリーをサポートしています。
サブセクションがカテゴリーとして扱われます。
サブセクションの更に下のセクションはサブカテゴリーとして扱われます。




