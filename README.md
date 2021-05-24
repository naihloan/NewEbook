# NewEbook
NewEbook

## Install pandoc and wget (or use cURL)

## Fetch web pages from a friendly blog that reviews books

`wget https://sive.rs/book/Mindwise https://sive.rs/book/ThinkingFastAndSlow https://sive.rs/book/StoicJoy https://sive.rs/book/TimeParadox https://sive.rs/book/StumblingOnHappiness https://sive.rs/book/EMythRevisited`

## Make sure that each fetched page has an .html extension, or else add it.

## Create items for a table of contents from fetched pages

ls >> 1-toc.md

The created table of contents file (toc.md) will contain a list of the fetched pages. Acces contents and add markdown notation to set them as table of contents. Create items as a bullet list to show chapters. Connect a reference that links each iece to chapters with hyperlinks. For each chapter add in one line each * + [name or chapter author] + (link). That is, from:

chapter.md

to:

* [Author or Title](chaptername.md)

## Create a yaml header in the top lines of your (tableofcontents).md file with metadata to add an initial title page:

---
title: "The best books that Derek Sivers Recommends and Reviewed"
author: Several Authors with notes from Derek Sivers' blog 
date: \today
---


## Convert each .html item to .md with pandoc:

pandoc chapter.html -o chapter.md

(you can also do this in batch mode, not documented here, yet)

(if every chapter has reviewer title you can remove that section manually in each .md chapter file to save visual space and avoid repetition)

## Add all parts into a single file

*.md >> ebook.md

## Convert them to ebook in different formats

pandoc ebook.md -o ebook.epub
pandoc ebook.md -o ebook.odt
pandoc ebook.md -o ebook.pdf

## To convert from markdown to .mobi use calibre:

ebook-convert "ebook.epub" "ebook.mobi"

===

Enjoy your new ebook. :) 
