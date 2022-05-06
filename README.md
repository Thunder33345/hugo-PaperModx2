# PaperModx2
> PaperModx2 is a theme for [Hugo](https://gohugo.io) forked from [Hugo PaperMod](https://github.com/adityatelange/hugo-PaperMod)

Goals: This is a personal fork I made for myself to play around with. And maybe add some features along the way.

Changes: you can see [CHANGELOG.md](CHANGELOG.md) for the changes and improvements

Stability: This project should not be considered as production ready, please use [Hugo PaperMod](https://github.com/adityatelange/hugo-PaperMod) instead.

## Configuration
bellow list configurable values added by this fork
## Site Config
Values configured via `config.*` at the root of your site

### TOC
`tocMinHeaders`(int) will hide toc if there's less then specified headers

`tocMinWords`(int) will hide toc if there's less then specified words

Both are OR-ed together, toc will be hidden if either of them is true

### 404 Message
`not_found_message` accepts a raw string including HTML codes.

### Front Matter
Values configured via a md file's front matter

## Custom page type
This is a collection of custom single paged layouts.
You can use this to overwrite certain pages and "break out" of traditional layout.

In order to use, in your front matter set the following code:
```yaml
type: "_custom"
layout: ""
_build:
  list: never
outputs:
- html
```
The type will always be `_custom`, you can find available layouts in `layouts/_custom/`.

The `_build.list: never` stops hugo from listing it as a normal page.

The `outputs` stop hugo from generating other variants like `xml` and `json` specifically for said page

## Minimal
This is a minimal layout without breadcrumbs, post meta, toc, taxonomy list, navlinks.

This is useful for creating a custom page with focus on content, like an "About" page.

Some stuff are enabled intentionally, comments, shareicon, title, description, etc.

## Archive
Archive is a page with a list of posts sorted by dates.

## Search
Search is a page that allows user to search thru the blog.

You will need to add `json` to the `outputs` to generate the index file used for searching. (search will not work without it, an error will be generated to assist you)

Example:
```yaml
---
title: "Search"
type: "_custom"
layout: "search"
url: "/search/"
summary: "search"
_build:
  list: never
outputs:
- html
- json
---
```
