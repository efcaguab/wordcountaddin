[![Travis-CI Build Status](https://travis-ci.org/benmarwick/wordcountaddin.svg?branch=master)](https://travis-ci.org/benmarwick/wordcountaddin)

<!-- README.md is generated from README.Rmd. Please edit that file -->
wordcountaddin
==============

This R package is an [RStudio addin](https://rstudio.github.io/rstudioaddins/) to count words and characters in selected text in an [R markdown](http://rmarkdown.rstudio.com/) document. It also has a function to compute readability statistics.

When counting words in your Rmd document, these things will be ignored:

-   YAML front matter
-   code chunks and inline code
-   text in HTML comment tags: `<!-- text -->`
-   inline URLs in this format: `[text of link](url)`
-   images with captions in this format: `![this is the caption](/path/to/image.png)`

And because my regex is quite simple, the word count function may also ignore parts of your actual text that resemble these things. The word count will include text in block quotations, verbatim code blocks, tables, raw LaTeX and raw HTML.

There are numerous ways to count words using R, depending on how you define a word and a sentence. I've included three methods here, mostly out of curiosity to see how they differ from each other. I use functions from the [stringi](https://cran.r-project.org/web/packages/stringi/index.html), [koRpus](https://cran.r-project.org/web/packages/koRpus/index.html) and [qdap](https://cran.r-project.org/web/packages/qdap/index.html) packages.

Inspiration for this addin came from [jadd](https://github.com/jennybc/jadd) and [WrapRmd](https://github.com/tjmahr/WrapRmd).

How to install
--------------

Install with `devtools::install_github("benmarwick/wordcountaddin",  type = "source")`

Go to `Tools > Addins` in RStudio to select and configure addins.

How to use
----------

1.  Open a Rmd file in RStudio.
2.  Select some text, it can include YAML, code chunks and inline code
3.  Go to `Tools > Addins` in RStudio and click on `Word count` or `Readability`. Computing `Readability` may take a few moments on longer documents.
4.  Look in the console for the output

Feedback, contributing, etc.
----------------------------

Please note that this project is released with a [Guide to Contributing](CONTRIBUTING.md) and a [Contributor Code of Conduct](CONDUCT.md). By participating in this project you agree to abide by its terms.
