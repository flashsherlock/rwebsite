---
title: Demo Markdown
author: Fei
date: '2020-05-02'
categories:
  - R
tags:
  - Markdown
weight: 2
disable_comments: true
---

This is a post written in plain Markdown (`*.md`) instead of R Markdown (`*.Rmd`). The major differences are:

1. You cannot run any R code in a plain Markdown document, whereas in an R Markdown document, you can embed R code chunks (```` ```{r} ````);
2. A plain Markdown post is rendered through [Blackfriday](https://gohugo.io/overview/configuration/), and an R Markdown document is compiled by [**rmarkdown**](http://rmarkdown.rstudio.com) and [Pandoc](http://pandoc.org).

There are many differences in syntax between Blackfriday's Markdown and Pandoc's Markdown. For example, you can write a task list with Blackfriday but not with Pandoc:

- [x] Write an R package.
- [ ] Write a book.
- [ ] ...
- [ ] Profit!

Similarly, Blackfriday does not support LaTeX math and Pandoc does. I have added the MathJax support to this theme ([hugo-lithium](https://github.com/yihui/hugo-lithium)) but there is a caveat for plain Markdown posts: you have to include math expressions in a pair of backticks (inline: `` `$ $` ``; display style: `` `$$ $$` ``), e.g., `$S_n = \sum_{i=1}^n X_i$`.^[This is because we have to protect the math expressions from being interpreted as Markdown. You may not need the backticks if your math expression does not contain any special Markdown syntax such as underscores or asterisks, but it is always a safer choice to use backticks. When you happen to have a pair of literal dollar signs inside the same element, you can escape one dollar sign, e.g., `\$50 and $100` renders "\$50 and $100".] For R Markdown posts, you do not need the backticks, because Pandoc can identify and process math expressions.

When creating a new post, you have to decide whether the post format is Markdown or R Markdown, and this can be done via the `ext` argument of the function `blogdown::new_post()`, e.g.

```r
blogdown::new_post("Post Title", ext = '.Rmd')
```
Images can be insert by `![]()` or a img tag.

```markdown
![pie](/post/2020-05-02-demo-markdown_files/pie-1.png)
```
 The img tag can also define the width of a figure.
 
```html
<img src="/post/2020-05-02-demo-markdown_files/pie-1.png" alt="pie" width="50%"/>
```

However, the width is defined by a attribute style in the tag, which can be overwrite by css styles. Therefore, a embedded style sheet should be used.

```html
<img src="/post/2020-05-02-demo-markdown_files/pie-1.png" alt="pie" style="width: 80%; display: block; margin:0 auto"/>
```

<img src="/post/2020-05-02-demo-markdown_files/pie-1.png" alt="pie" style="width: 80%; display: block; margin:0 auto"/>
