# jekyll-news-example

Running locally:

```
# Install ruby dependencies
bundle install

# Serve website locally
bundle exec jekyll serve
```


## Discussion

Administering the static site can be done quickly and easily on github, taking advantage of versioning, PR, and other features. Github pages can quickly deploy the website both in staging and in production.


### Content administration
Content is added to the site by adding a `post` in the `_posts/news` directory.

```md
---
title: Your news title
layout: news-post
---

Your news *with markdown* <b>and HTML if you want</b>.
```


### Layout/style administration

What the site looks like is easily modified via the `_layouts` and snippets included via `_includes` in a jinja-like template language called liquid. The language and the variables populated by jekyll are well described in the [jekyll documentation](https://jekyllrb.com/).

Content doesn't just need to be news, it can be all forms of different "posts" which get rendered and aggregated differently with the help of `layout`. See `_includes/news.html` to see how all news posts can be listed one by one.

### Staging

Github actions have been set up to deploy all branches to the site's `staging/{branchname}` subdirectory, this lets you work on and view branches before they make it to production. Code pushed to `main` will update production.
