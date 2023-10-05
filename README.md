---
bibliography: 'Z:\My Drive\ZoteroBBT.bib'
title: 'Collaborative academic writing'
...

Academics spend a lot of their time writing papers, proposals, reports and other documents. Many are happy with traditional workflows combining commercial word processors (e.g. Word) and a bibliography solution such as Zotero or Mendeley. 
But academic writing is often collaborative, so that a lot of researchers actually use Google Docs (and its bibliography plugins) rather than these traditional offline solutions.
Yet, Google Docs does not offer the best guarantees when it comes to privacy, and it is rather limited when it comes to templating, writing equations or simply using it offline.

This tutorial is obviously a lot more complex than logging in Google and open a Google Doc, but it might be of interest for those who look for a more modern and efficient, privacy-conscious workflow, enabling real-time collaborative writing. Carefully implemented, this pipeline might be particularly useful for researchers who wish to move away from Google Docs for whatever reason without losing functionality (in fact, they will gain functionality). Last but not least, this pipeline relies entirely on **free, open-source** software!

The tutorial is divided in several parts: introduction, software installation and configuration, test and comments.

## Introduction
Markdown is at the heart of our approach. It is *the* markup language that allows extremely quick and reproducible writing. Markdown is mostly defined by its syntax, where different symbols activate different functions. For example, the symbol # can be used to create titles of different size. # Will produce a huge title, whereas #### will produce a much smaller title. Symbols like \*, \_ , \~ or \^ allow to write bold, italics, subscript or superscript characters. Messaging apps like What's App also use some of these syntactic shortcuts, but Markdown goes much farther and allows to create citations, URL links, tables, lists, figures, etc using a similar approach. The [Markdown website](https://www.markdownguide.org/) is a good place to get started. Note that Github and many other Web development tools apps use Markdown routinely. Furthermore, Markdown allows templating much like conventional word processors (i.e. choice of fonts, font style, color, etc.).

However, as efficient as it can be, Markdown alone is not sufficient for academic writing.
1. First of all, one needs to chose an editor to create and write .md files. For this, we will use [Visual Code](https://code.visualstudio.com/) for its stability and its versatility (thanks to its amazing set of extensions).
2. Second, one needs to install and configure some tool to manage citations and bibliographies. For this, we will use [Zotero](https://www.zotero.org/) which has also an excellent support and great extensions.
3. Third, one needs to install and configure some tool to export .md Markdown files to other formats such as .pdf, .dox or event .html files. For this, we will use the universal document converter [Pandoc](https://pandoc.org/).
4. Fourth, one needs to set up the LiveShare extension of Visual Code in order to allow real-time collaborative writing. This extension also allows real-time collaborative coding. It is very well maintained by Microsoft and it is free.
5. Along the way, we may install other optional software such as [MikTex](https://miktex.org/) to facilitate the writing of equation and export to PDF, or [Mermaid](https://mermaid.js.org/) to write down graphs in Markdown.

## Installation and configuration

Please install Visual Code, Zotero and Pandoc using the links provided above. If you want to export directly to PDF and/or write nice equations, install MikTex as well.

### Set up Visual Code

When working with Visual Code, you'll always have to open a base folder first (File menu). Think of your base folder as a unit that may be uploaded online (e.g. on Github or else) and shared with collaborators. Try to define these base folders as folders that represent autonomous projects (e.g. a research paper, an analysis pipeline, a website, etc.).
Anyway, at this stage, what matter is more to install the adequate extensions for VS code (just click the install button and continue). Click on the following links to install each extension (the order does not matter).
- [Markdown Lint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint): a nice tool to check the validity and quality of your Markdown syntax.
- [VScode-pandoc](https://marketplace.visualstudio.com/items?itemName=DougFinke.vscode-pandoc): a useful extension to automatize the exportation of documents written in Pandoc.
- [Citation Picker for Zotero](https://marketplace.visualstudio.com/items?itemName=mblode.zotero): a small utility to grab references from Zotero and include them in your Markdown files, exactly as you would do in Word or Google Docs.
- [Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare): a very fancing real-time collaborating app for Visual Code. Note that, unlike collaboration based on Google Docs, Live Share can be set to work **exclusively** with direct connection (no data or text transits through the cloud, Internet is only required to log into the service). Live Share is therefore compatible with the privacy demands that some of us might worry about.


Many other useful extension are available 

2. Install markdownlint: <https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint>
3. [@ligneul2019]
