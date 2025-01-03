---
layout: post
title: Using Jekyll
# description: Examples of Jekyll
# author: khoa_pham
date: 2025-01-03 09:00 -0800
categories: [Tutorials, Jekyll]
tags: [tutorials, notes]
# pin: true
---

# Jekyll

```terminal
bundle

bundle exec jekyll serve
```

## New Posts
[Writing a New Post](https://chirpy.cotes.page/posts/write-a-new-post/)

<https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/_posts/2019-08-08-write-a-new-post.md?plain=1>

### Create a New Post
[Jekyll Compose](https://github.com/jekyll/jekyll-compose)


```console
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

```markdown
<!-- Block math, keep all blank lines -->

$$
LaTeX_math_expression
$$

<!-- Equation numbering, keep all blank lines  -->

$$
\begin{equation}
  LaTeX_math_expression
  \label{eq:label_name}
\end{equation}
$$

Can be referenced as \eqref{eq:label_name}.

<!-- Inline math in lines, NO blank lines -->

"Lorem ipsum dolor sit amet, $$ LaTeX_math_expression $$ consectetur adipiscing elit."

<!-- Inline math in lists, escape the first `$` -->

1. \$$ LaTeX_math_expression $$
2. \$$ LaTeX_math_expression $$
3. \$$ LaTeX_math_expression $$
```