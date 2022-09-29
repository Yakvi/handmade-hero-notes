# Handmade Hero Notes - Contributing Guide

![Handmade hero Notes](media/logo.png)

You can contribute to Handmade Hero Notes in one or more fields outlined below. 

For more considerable contributions, an essential prerequisite is to join the project [Discord](https://discord.gg/Vnvc8QD) server and coordinate your intentions with the other members to prevent double work from being done. 

## Bug Fixing

If you found a typo or a similar minor bug, create an issue on GitHub or report it on the discord `bugs-and-typos` channel.

## Style

If you'd like to improve the project's style, please modify both [style.css](css/style.css) and [html-style.css](css/html-style.css). These two stylesheets control the styling in the `.md.html` and the `.html` files. 

## Day

If you'd like to write a brand new Day or have a significant expansion of an existing day, please coordinate with the other contributors in the `#contributions` channel on Discord. You can then develop the Day in [Markdeep](https://casual-effects.com/markdeep/features.md.html) (type [?noformat](https://casual-effects.com/markdeep/features.md.html?noformat) to see the usage of the various features) in dayXXX.md.html. 

Each Day's work can contain the following subparts. You can decide to work on a whole Day or a specific subpart.

### Day Setup

Initialize each Day using the templates provided in the [templates](/templates) folder. 

* `dayXXX.html` should go inside [html](/html) folder. You should replace `XXX` and `YYY` with correct links to the previous and next days, respectively.
* `refs_dayXXX.md.html` should go inside [articles/references](/articles/references) folder.
* `glossary_dayXXX.md.html` should go inside [articles/glossary](/articles/glossary) folder.
* `dayXXX.md.html` should go inside [articles](/articles) folder. You should:
    * replace `XXX` with the current Day, add the title of the Day as written in the [Episode Guide](https://hero.handmade.network/episode/code)
    * add the length of the original video and ensure the link to it works correctly.
    * replace `YYY` with the previous Day, add the title.
    * replace `ZZZ` with the following Day, add the title.
    * link with the `refs` and `glossary` files.
    * verify that the page loads correctly in the browser and that all the dependent files are linked correctly.
* Add the link to the Day inside [links.md.html](/articles/links.md.html). 

### Code 

The code for is written in a way that would enable reader to follow what's happening with ease. 

* Additions, edits and deletions should be fenced as `C++ add`, `C++ edit` or `C++ delete` respectively. 
* Every code change should be commented with a caption `[Listing [x]: <file>[filename]</file> Describing the change in gerund.]` where `x` should be left as is in most cases (unless you want to link to a specific listing, in that case you can give it a unique identifier). If a code change happens inside a specific function, and the function signature is not visible in the code block, `<file>` block becomes `[filename > NameOfTheFunction]`. 

### Main Thought Line

The code descriptions and the thought process for the main topic of the Day is the heart of _Handmade Hero Notes_. You should subdivide the Day into sections and subsections, provide the most complete and exhaustive (without going towards boring) description of everything that's going on, how and why. 

You should make use of a grammar-checking and spellchecking tool like [Grammarly](https://www.grammarly.com/).

### Charts and Illustrations

Enriching the text and code with illustrations helps better understanding the topic, and you should strive to make it as clear as possible.

You can develop charts directly using [Markdeep](https://casual-effects.com/markdeep/features.md.html). Upon the export, they're converted to SVG so they're quite lightweight in size. 

If you add any external media (pictures, gifs, etc.) you should create a corresponding directory in the [media](/media) folder and put your files there. Having pictures saved locally is preferred to just linking them across the web, with focus on smaller file sizes.

### Off-topic

There're three major off-topic sections that might or might not appear during the Day: 

* __Programming Notions__: Introduction to a specific concept that would be prerequisite to understanding the topic of the Day (for example, floating-point numbers when speaking about floating-point math). Each notion should be covered only once, the first time you encounter it.
* __Side Considerations__: Any offtopic matter, code change, discussion that Casey covered during the main stream (not Q&A) but that otherwise would break the flow of the main topic. 
* __Bugfix__: Still being defined, this section is aimed to display solutions for minor bug hunting that is left as "exercise to the reader" in the main section. 

Unless it's completely off-topic, every subsection of these should be cross-linked with the main chapter ("to learn more, head over subsection XXX" and then "Back to subsection YYY"). 

### References and Glossary

References file should contain all the external links mentioned during the Day, and each reference should be mentioned at least once inside a given day. 

In an ideal world, Glossary should be expanded, and each term given a single-sentence definition with a link to an external resource to learn more (Wikipedia, cppreference, etc.)


### Day Export

After all the work has been completed on a Day, it should be correctly exported as a static `.html` file and integrated in the book.

To do so, you need to: 

1. Export `.md.html` as `.html` by adding `?export` suffix to the page address.
2. Copy and paste all of the export inside `dayXXX.html` file (after the existing template things)
3. Replace the header of the html with the one in template.
4. Replace the TOC line with the one in template.
5. Add the Day to [index.md.html](/index.md.html) and [index.html](/index.html) (note that in both locations you should link to the exported file)
6. Add the `refs` and `glossary` files to [appendix.md.html](/articles/appendix.md.html).