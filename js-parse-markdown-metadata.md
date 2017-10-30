<!-- @meta
Title: Introducing js-parse-markdown-metadata
Author: Ryan K Harris
Keywords: javascript markdown npm node
Created: 23Oct2017
Updated: 23Oct2017
Version: 0.3.1
-->


## Summary
`js-parse-markdown-metadata` is a Node.js module for parsing metadata content from markdown content.

## References
- on [NPM](https://www.npmjs.com/package/js-parse-markdown-metadata "js-parse-markdown-metadata on NPM")
- on [GitHub](https://github.com/ryankharris/js-parse-markdown-metadata "js-parse-markdown-metadata on GitHub")

## The why
In the process of writing [grokblarg](https://github.com/ryankharris/grokblarg "grokblarg on GitHub") I did try a few other metadata parsers before writing my own, and either they didn't work at all, or worked in a way I didn't care for. The thing I primarily disliked were the metadata tag formats prescribed, which were usually something like:

    === / ===
    $$$ / $$$
    <!-- / -->
    etc.

Now, I have two primary editors which I use for writing markdown. Both include a 'Preview' frame showing the styled output, and both of them choke on anything except the `<!--` `-->` combination. All of the other custom tag combinations already mean something in Markdown (vanilla or a superset), or won't be ignored. I do want my metadata ignored by parsers that don't understand it, which means you have to wrap the custom tags in a comment pair anyhow.

One of the primary work-flow issues I found while writing documents recently was commenting-out old/alt versions of text while updating an .md document. I want to be able to make use of the `<!--` `-->` tags to comment out sections while also wrapping metadata with them for the reasons above, hence the addition of the `@meta` annotation to my module. Plus I just like the way it reads.

Further, js-parse-markdown-metadata allows you to pepper metadata throughout your doc (if you were so inclined), not just at the top, in one set of tags. I don't have a use case for that necessarily, but it just stood out as something that I wanted.

The end result is something like the metadata for this post:

    <!-- @meta
    Title: Introducing js-parse-markdown-metadata
    Author: Ryan K Harris
    Keywords: javascript markdown npm node
    Created: 23Oct2017
    Updated: 23Oct2017
    Version: 0.3.1
    -->

I hope people find it useful and create issues/pull-requests as they find them!
