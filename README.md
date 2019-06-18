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
- Eyecache Image
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
    profile_image = ""
```

### Author

```toml
[Params]
    author = "Your Name"
```

### Eye Cache Image

```toml
[Params]
    eyecatch = "images/eyecache.jpg"
```

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

## Example

```toml
baseURL = "http://example.org/"
title = "Basic Design Personal Blog"
disablePathToLower = true
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
### Recommended permalink format

```
[permalinks]
    post = "/:section/:year/:month/:filename"
```

By default, subsections are included in the path, so
If you move an article to another subsection, the URL changes.

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
Subsections are treated as categories.
The sections further down the subsection are treated as subcategories.



