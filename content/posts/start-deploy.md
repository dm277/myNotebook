---
title: "Deploy Site online - how to?"
date: 2023-06-04T07:31:51+02:00
draft: true
featured_image: '/images/settings.jpg'
---

In this post, we will be deploying the site that we created using a free account at Netlify. The site will be re-built and re-deployed whenever we push a new commit to our site’s Git repository. We will also look at how to set up our site using our own domain and create an SSL certificate.

A question that comes up a lot when I talk about deploying static sites like Hugo with Netlify is why not just use GitHub Pages?

This is a great question. While GitHub Pages allows us to deploy our site with a custom domain and SSL, it does not let us deploy a staging or preview version of the site to test out changes before making them live. Netlify gives us the ability to create a preview site for each pull request which I use to see what my future and draft post will look like on a machine other than my laptop. Netlify also allows us to deploy a branch to a subdomain, allows multiple domains pointing to a single site, unlimited websites, and rollback to a previous build. All of this can be done with the free tier of Netlify.

```
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```

### Add a new page to your site.

`hugo new posts/my-first-post.md`
Hugo created the file in the content/posts directory. Open the file with your editor.

Add some markdown to the body of the post, but do not change the draft value.

```
---
title: "My First Post"
date: 2022-11-20T09:03:20-08:00
draft: true
---

## Introduction

This is **bold** text, and this is *emphasized* text.

Visit the [Hugo](https://gohugo.io) website!
```

Save the file, then start Hugo’s development server to view the site. You can run either of the following commands to include draft content.

```
hugo server --buildDrafts
hugo server -D
```

View your site at the URL displayed in your terminal. Keep the development server running as you continue to add and change content.

