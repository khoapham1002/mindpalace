---
layout: post
title: Using Jekyll
date: 2025-01-03 09:00 -0800
categories: [Tutorials, Jekyll]
tags: [tutorials, notes]
---

# Jekyll

```terminal
bundle

bundle exec jekyll serve
```

## New Posts
[Writing a New Post](https://chirpy.cotes.page/posts/write-a-new-post/)
<https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/_posts/2019-08-08-write-a-new-post.md?plain=1>


```YAML
layout: post                                   # Optional
title: Post Title
date: YYYY-MM-DD HH:MM:SS +/-TTTT              #-0800 is PST timezone
categories: [TOP_CATEGORIE, SUB_CATEGORIE]     # Only 2 elements
tags: [TAG]                                    # lowercase; infinite elements
author: <author_id>                            # for single entry
authors: [<author1_id>, <author2_id>]          # for multiple entries
description: Short summary of the post.        # Optional
toc: false                                     # Table of contents
comments: false
pin: true                                      # Pin to the top of homepage
image:                                         #image: /path/to/image
  path: /path/to/image
  alt: image alternative text
#   lqip: /path/to/lqip-file                   # or base64 URI
math: true
# mermaid: true
```

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
<!-- Image -->
![img-description](/path/to/image)
_Image Caption_

<!-- Size -->
![Desktop View](/assets/img/sample/mockup.png){: width="700" height="400" }     <!--w="700" h="400" works too!-->


<!-- Video -->
{% include embed/video.html src='{URL}' %}
<!-- URL: /path/to/sample/video.mp4 -->
{%
  include embed/video.html
  src='/path/to/video.mp4'
  types='ogg|mov'
  poster='poster.png'
  title='Demo video'
  autoplay=true
  loop=true
  muted=true
%}

{% include embed/{Platform}.html id='{ID}' %}
Video URL	                                    Platform	ID
https://www.youtube.com/watch?v=H-B46URT4mg	    youtube	    H-B46URT4mg
https://www.twitch.tv/videos/1634779211	        twitch	    1634779211
```

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