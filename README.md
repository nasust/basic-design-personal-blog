# Hugo Theme Basic Design Personal Blog

This is a simple blog theme.
It has a plain design for easy customization.

## Features

- HTML5
- SCSS
- AMP
- Responsive
- Hierarchy Categories
- Tags
- Featured Images
- Global Menu

## Installation

```shell
$ cd themes
$ git clone git@github.com:nasust/basic-design-personal-blog.git
```

## Configuration

### Output AMP

```toml
[outputs]
    page = [ "HTML" , "AMP"  ]
```

### Profile Avatar Image

```toml
[Params]
    profile_image = "images/avatar_image.jpg"
```

put ``assets/images/avatar_image.jpg``

### Author

```toml
[Params]
    author = "Your Name"
```

### Featured Image

```toml
[Params]
    featured_image = "images/featured_image.jpg"
```
Specifies the default image if no featured image is specified in Markdown.

put ``assets/images/featured_image.jpg``

### Global Menu

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

### Example

```toml
baseURL = "http://example.org/"
title = "Basic Design Personal Blog"
languageCode = "en-us"
defaultContentLanguage = "en"
disablePathToLower = true
pluralizeListTitles = false
pygmentsUseClasses = true
pygmentsCodefences = true
theme = "basic-design-personal-blog"

[outputs]
    page = [ "HTML" , "AMP"  ]

[Params]
    author = "Hoge"
    profile_image = "images/profile.jpg"
    featured_image = "images/featured_image.jpg"

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

### Recommended permalink format

```toml
[permalinks]
    post = "/:section/:year/:month/:filename"
```

By default, subsections are included in the path, so if you move an article to another subsection, the URL will change.

## Hierarchy Categories

```bash
content
└── post
    ├── general --------------- category
    ├── cateogry_1 ------------ category
    │   ├── sub_category_1 --- sub category
    │   └── sub_category_2 --- sub category
    └── cateogry_2 -------------category
```

Supports hierarchical categories. 
The subsections are treated as categories. 
Sections further down the subsection are treated as subcategories.

## Markdown Front Matter

### featured image

```yaml
featured_image: "featured_images.jpg"
```

set featured image

featured image lookup order

1. page bundles
2. assets

### tags

```yaml
tags: ["tag 1" , "tag 2"]
```

### Example

```yaml
title: "blog title"
date: 2019-06-17
draft: false
featured_image: "featured_images.jpg"
tags: ["general" , "poem" ]
```

