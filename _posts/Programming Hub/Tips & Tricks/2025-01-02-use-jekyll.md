---
layout: post
title: Use Jekyll
date: 2025-01-02 09:00 -0800
description: Examples of using Jekyll
authors: [cotes, khoa_pham]
categories: [Programming Hub, Tips & Tricks]
tags: [blogging]
pin: false
math: true
mermaid: true
toc: true
comments: true
image:
  path: https://chirpy-img.netlify.app/commons/devices-mockup.png
  # lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Responsive rendering of Chirpy theme on multiple devices.
---

Links to Chirpy setup:
> [Chirpy Theme Page](https://chirpy.cotes.page)  
> [Jekyll & Ruby Setups](https://jekyllrb.com/docs/installation/)  
> [Chirpy GitHub Repository](https://github.com/cotes2020/jekyll-theme-chirpy/wiki)

<!-- --- -->

## Running Locally   
Links to test locally:  
> <http://127.0.0.1:4000/>  
> <http://127.0.0.1:4000/mindpalace/>  

```shell
bundle install
```


### Start the Jekyll Server   
```shell
bundle exec jekyll serve
```

After adding shortcuts to `code ~/.zshrc` file:
```shell
jserve
```


## Managing Posts   
> Link to [Jekyll Compose](https://github.com/jekyll/jekyll-compose)


### Create a Post   
```bash
bundle exec jekyll post "My New Post"
bundle exec jekyll compose "My New Post"
```

After adding shortcuts to `code ~/.zshrc` file:
```shell
jpost My New Post
```


### Other Commands   
```bash
bundle exec jekyll draft "My new draft"
```

```bash
bundle exec jekyll page "My New Page"
```

```bash
bundle exec jekyll rename _posts/2014-01-24-my-new-draft.md "My New Post"
```

```bash
bundle exec jekyll unpublish _posts/2014-01-24-my-new-draft.md
```


## Front Matter   
```yaml
---
layout: post
title: TITLE
date: YYYY-MM-DD HH:MM:SS +/-TTTT
description: Short summary of the post.
categories: [Top_Categ, Sub_Categ]
tags: [tag1, tag2, tag3, tag4]
authors: [<author1_id>, <author2_id>]
toc: true
comments: false
pin: true
math: true
mermaid: true
image:
  path: /path/to/image
  alt: image with 1200 x 630 or "1.91 to 1" aspect ratio
---
```


#### Author Information   
```yaml
<author_id>:
  name: <full name>
  twitter: <twitter_of_author>
  url: <homepage_of_author>
```
{: file="_data/authors.yml" }


## Use Markdown 
> Link to [Use Markdown](https://khoapham1002.github.io/mindpalace/posts/use-markdown/)  
