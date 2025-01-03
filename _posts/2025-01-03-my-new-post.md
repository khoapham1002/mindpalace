---
layout: post
title: My New Post
date: 2025-01-03 09:42 -0800
categories: [Animal, Insect]
tags: [bee]
---

# Categories and Tags
The categories of each post are designed to contain up to two elements, and the number of elements in tags can be zero to infinity. For instance:


## Front Matter

```
bundle exec jekyll serve
```

```console
title: TITLE
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [TAG]     # TAG names should always be lowercase
```

### Timezone of Date

To accurately record the release date of a post, you should not only set up the timezone of _config.yml but also provide the post’s timezone in variable date of its Front Matter block. Format: +/-TTTT, e.g. +0800.