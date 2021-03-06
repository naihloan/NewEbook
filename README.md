# NewEbook

Fetch web material and create an ebook from scraped texts. From HTML collected texts you can create sections for a brand new ebook to read on your digital device. Follow these steps to create your customized book chapters.

## Install pandoc, calibre, and wget (or use cURL)

## Fetch web pages from a friendly blog that reviews books

`wget https://sive.rs/book/Mindwise https://sive.rs/book/ThinkingFastAndSlow https://sive.rs/book/StoicJoy https://sive.rs/book/TimeParadox https://sive.rs/book/StumblingOnHappiness https://sive.rs/book/EMythRevisited`

## Make sure that each fetched page has a .html extension, or else add it.

You can do this manually, or in batch. One option is using a combination of ranger file manager and vim annotations to make a bulkrename. If you visually select all files you can add a custom format at the end of each filename. 

`chapter1` becomes `chapter1.html`

## Create items for a table of contents from fetched pages

`ls >> 1-toc.md`

The created table of contents file (1-toc.md) will contain a list of the fetched pages. Access contents and add markdown notation to set them as a table of contents. Create items like a bullet list to show chapters. Connect a reference that links each piece to chapters with hyperlinks. For each chapter add, in one line each: * + [name or chapter author] + (link). That is, from:

from `chapter.md` to each line in a single row:

* `[Author and Title](chaptername.md)`
* `[Following Author and Title](chaptername-n2.md)`
* `[Following Author and Title](chaptername-n3.md)`

## Create a YAML header in the top lines of your (table of contents).md file with metadata to add an initial title page:

```
---
title: "Best books Recommended and Reviewed"
author: Several Authors with notes from Derek Sivers' blog 
date: \today
---
```

## Convert each .html item to .md with pandoc:

`pandoc chapter.html -o chapter.md`

(you can also do this in batch mode, not documented here, yet)

(if every chapter has a reviewer title you can remove that section manually in each .md chapter file to save visual space and avoid repetition)

## Add all parts into a single file

` *.md >> ebook.md`

## Convert them to ebook in different formats

```
pandoc ebook.md -o ebook.epub
pandoc ebook.md -o ebook.odt
pandoc ebook.md -o ebook.pdf
```

## To convert from markdown to .mobi use calibre:

`ebook-convert "ebook.epub" "ebook.mobi"`

===

Enjoy your new ebook. :) 
