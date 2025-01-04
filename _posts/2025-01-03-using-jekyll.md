---
layout: post
title: Using Jekyll
description: Examples of Jekyll
author: khoa_pham
date: 2025-01-03 09:00 -0800
categories: [Tutorials]
tags: [tutorials, notes]
pin: true
---

## Understand Basics

```bash
bundle

bundle exec jekyll serve
```

[Writing a New Post](https://chirpy.cotes.page/posts/write-a-new-post/)

<https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/_posts/2019-08-08-write-a-new-post.md?plain=1>

[Jekyll Compose](https://github.com/jekyll/jekyll-compose)


### Create a New Post

```terminal
bundle exec jekyll post "My New Post"
bundle exec jekyll post "My New Post" --timestamp-format "%Y-%m-%d %H:%M:%S %z"

bundle exec jekyll compose "My New Post"
# bundle exec jekyll compose "My New Post 1" --post
# bundle exec jekyll compose "My New Post 2" --collection "posts"
```

### Rename a Post

```console
bundle exec jekyll rename _posts/2014-01-24-my-new-draft.md "My New Post"
bundle exec jekyll rename _posts/2014-01-24-my-new-draft.md "My New Post"
bundle exec jekyll rename _posts/2014-01-24-my-new-draft.md "My New Post"
```

### Writing Markdown

***Term 1***
: ~~Definition of term 1~~

**Term 2**
: _Definition of term 2_

- Item 1
  - Item 2
    - `Sub-item`

1. Item 1
2. Item 2
3. Sub-item

- [ ] Job
  - [x] Step 1
  - [x] Step 2
  - [ ] Step 3

> Link to [Google](https://www.google.com)

Link to more info in this [README.md](/README.md)

---

| Header 1 | Header 2 |
| -------- | -------- |
| Row 1 Col 1 | Row 1 Col 2 |
| Row 2 Col 1 | Row 2 Col 2 |


| Left Aligned | Center Aligned | Right Aligned |
|:------------ |:--------------:| -------------:|
| Row 1 Col 1  | Row 1 Col 2    | Row 1 Col 3   |
| Row 2 Col 1  | Row 2 Col 2    | Row 2 Col 3   |

***

This is an inline equation: $E = mc^2$.

This is a displayed equation:
$$
a^2 + b^2 = c^2
$$
