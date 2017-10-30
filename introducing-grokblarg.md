<!-- @meta
Title: Introducing grokblarg
Author: Ryan K Harris
Keywords: grokblarg blog
Created: 21Oct2017
Updated: 21Oct2017
Version: 0.3.1
-->


[grokblarg](https://github.com/ryankharris/grokblarg "grokblarg") is my first attempt at a static-content-generator to use with GitHub pages. Initially I was adding this dev-log-content to an .md file that would live alongside the README or intro content, but realized this can simply be my first post ever! That's kinda meta right, the initial post of a blog being about writing the code to produce the blog...

The idea wasn't anything original: build a blog! But I wanted to make use of github pages for hosting and build a static-content blog, i.e. just .html pages, no server-side component.
But there's [Jekyll](https://github.com/jekyll "Jekyll") for that. So then why do it? I guess just because. Oh and to try it in JavaScript and Node.js.

I wanted to write posts as markdown and generate HTML from the markdown. I like minimal, semantic styling. So currently it is a CLI tool built using [Commander](https://www.npmjs.com/package/commander "Commander") that offers some basic setup, creation, and generation commands. The conversion from markdown to HTML is handled by [marky-markdown](https://www.npmjs.com/package/marky-markdown "marky-markdown"). The markdown metadata used within each source post file is parsed by [js-parse-markdown-metadata](https://www.npmjs.com/package/js-parse-markdown-metadata "js-parse-markdown-metadata"), a module I created and will write about in another post.

Planned features are keyword filtering, text search, and additional CLI commands.
