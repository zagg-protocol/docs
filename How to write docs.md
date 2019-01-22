How to write docs
There are a few conventions when writing docs that go into the Stellar Developers site. Most of the docs are written in Markdown format. For an introduction to Markdown, take a look at Github's Mastering Markdown Guide.

Headers
Lines that start with a hash symbol (#) are considered headers. Below is an example of a few and the name of the header:

# h1
## h2
### h3
#### h4
DO NOT use h1 since that is reserved for the page title generated from front matter.
DO NOT skip a header size (don't go from h2 to h4).
DO use smaller headers (more hash symbols) to represent that a section is nested under a parent one with a larger header.
DO add a space after the hash symbols. Some Markdown parsers will not render the text as a header without the space.
Front matter
At the top of most documents is something called "front matter". This is metadata for the file written in YAML format.

Here is an example of front matter in action:

---
title: Horizon Reference
---
The currently used keys in the front matter are:

title
Document title
Do not start a page with a Markdown header (# Title). Instead, leave it in the front matter. The developers site will take the title from the front matter.

Links
Use inline links and not reference links.

There are three different kinds of links, and each different kind of link has a significant meaning. Some of these links are transformed in the generation of the developers site.

link type	where to use	markdown link example	resulting link (after dev portal processing)
Relative	
links within same repository
../reference/accounts-all.md	../reference/accounts-all.html
Root relative	
when you want to use the GitHub file viewer (e.g. for source files)
/src/ledger/AccountFrame.cpp	https://github.com/stellar/CURRENT-REPOSITORY/tree/master/src
Absolute links	
cross repository links (should link to the dev portal at www.stellar.org/developers/)
links to external sites (like https://www.google.com/)
https://www.stellar.org/developers/js-stellar-base/learn/building-transactions.html	https://www.stellar.org/developers/js-stellar-base/learn/building-transactions.html
Non-markdown files
Sometimes we want to include other types of content such as .pdf's. To add front matter to the PDF, create a sibling file with the PDF file name and an added extension of .metadata. This file can then define metadata for the title of the .pdf.

An example can be seen in stellar-core's software folder.
