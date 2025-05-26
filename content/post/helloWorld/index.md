+++
date = '2025-05-16T19:31:36-04:00'
draft = false
title = 'Hello World + Style'
slug = 'hello-world'
categories = 'blog'
toc = true
description = 'So this is a description'
+++

I just want to see how a summary works. 
Denote a summary in several ways in Hugo. 
This particular summary is created by typing in the body, 
just below the front matter, and indicated when the summary is 
complete manually with this html comment looking thingy: <\!--more-->

Without escaping it, of course.

<!--more-->

# Hello World
## Hugo is a markdown-first static site generator.
Markdown is simple to create text content with. It is now a popular choice for 
static websites.
Out of the box, Hugo supports the CommonMark specification/Github flavors + some extensions. 
I've tried consulting the CommonMark Spec, but man. It'd be nice if the document itself was a little 
easier to use.

Hugo also has a reputation for bad documentation. I think this has changed as time has passed. 
I haven't found the documentation especially poor or even sort-of poor. At least it is formatted in a way that is easy to read. 
Sometimes, I prefer sparser docs with better formatting to more thorough docs with bad formatting.
My eyes want to give up pre-emptively whenever I need to consult a doc where the font is really squished, tiny, and the 
syntactical elements are not spaced well, causing them to appear to bleed into each other. Not sure where the consensus is out 
on that. Could just be a nitpick of mine. 

## This is a Second-Level Header
Getting started with Hugo has been really easy thanks to the community of theme-builders. 
Thank you. Without you, I'd have had to learn some Golang first, looooool.
This beautiful theme is by Jimmy Cai. Customized slightly by yours truly.

### Header 3
Just a header demonstration.

#### Header 4
Just another header demonstration

## Callout Blocks
I have used Obsidian for notes for several years by now. One thing that's 
been a bit of an adjustment in Hugo is that it doesn't natively support callout blocks. 
I guess that's not a markdown standard, but it's nice to have. It is possible to define your own 
callout blocks or to use someone else's callout block module. I'll eventually do one of those 
options because I cannot live without callout blocks anymore, lol.

In my search for information on this issue, I found this interesting post:
[https://toast.al/posts/softwarecraft/2023-08-29_semantic-markup-for-callouts/](https://toast.al/posts/softwarecraft/2023-08-29_semantic-markup-for-callouts/)
calling for the addition of a standard callout element to html. It also provides some helpful ideas for implementation 
of callouts, listing the pros and cons of several prominent examples.

## Definition list
 Supposedly, this is an extension enabled by default.
Let's give it a try.

```markdown
**Apple**
:   Pomaceous fruit of plants of the genus malus in the family Rosaceae
:   An American computer company
```

**Apple**
:   Pomaceous fruit of plants of the genus malus in the family Rosaceae
:   An American computer company

**Orange**
:    The fruit of an evergreen tree of the genus Citrus.

Definitions can span multiple lines.

**Multiple-line-definitions**
:   if the definition spans more than one line, you should indent 
    on each line. However, the indent is not required


**Multi-paragraph-definitions**
:   definitions can contain multiple paragraphs. But I think you may have to 
    remember to put a space between the term and the definition so that 
    the renderer wraps the definition paragraph in p tags.

    1. lists
    2. are supposed to work

    >blockquotes
    > too

    Definitions render inside of dl tags. I customized the css to center text 
    in main articles. I made a few exceptions -- one of which is that text inside of a dl tag is left-justified. 
    This is to preserve the format of the dictionary entries.

---

## Tables
I want to see how they render

| Italics   | Bold     | Code   |
| --------- | -------- | ------ |
| _italics_ | **bold** | `code` |

Alright, that's slightly different from the Obsidian variety that I'm used to.
Here's the code
```markdown
| Italics   | Bold     | Code   |
| --------- | -------- | ------ |
| _italics_ | **bold** | `code` |
```

Apparently, it supports alignment options with the `:` character

| #  | Item        | Left aligned | Center aligned |   Right aligned|
| -- | ----------- |:-------------|:--------------:| --------------:|
| 1. | First item  | some text    | more text      | even more text |
| 2. | Second item | some text    | more text      | even more text |
| 3. | Third item  | some text    | more text      | even more text |


```markdown
| #  | Item        | Left aligned | Center aligned |   Right aligned|
| -- | ----------- |:-------------|:--------------:| --------------:|
| 1. | First item  | some text    | more text      | even more text |
| 2. | Second item | some text    | more text      | even more text |
| 3. | Third item  | some text    | more text      | even more text |
```
---

## Diagrams
Now this is something new to me. Hugo supports [goat](https://github.com/bep/goat) diagrams.
Does not automagically render Mermaid, which I've used in Obsidian before. 
You can still make a Mermaid diagram, but it requires an *explicit* render hook.

```goat
      .               .                .               .--- 1          .-- 1     / 1
     / \              |                |           .---+            .-+         +
    /   \         .---+---.         .--+--.        |   '--- 2      |   '-- 2   / \ 2
   +     +        |       |        |       |    ---+            ---+          +
  / \   / \     .-+-.   .-+-.     .+.     .+.      |   .--- 3      |   .-- 3   \ / 3
 /   \ /   \    |   |   |   |    |   |   |   |     '---+            '-+         +
 1   2 3   4    1   2   3   4    1   2   3   4         '--- 4          '-- 4     \ 4
```
These render implicitly just as long as they are in a code block marked as goat code.
```markdown
I designated this block as markdown instead of goat, 
so the diagrams do not render with svg automagically.

      .               .                .               .--- 1          .-- 1     / 1
     / \              |                |           .---+            .-+         +
    /   \         .---+---.         .--+--.        |   '--- 2      |   '-- 2   / \ 2
   +     +        |       |        |       |    ---+            ---+          +
  / \   / \     .-+-.   .-+-.     .+.     .+.      |   .--- 3      |   .-- 3   \ / 3
 /   \ /   \    |   |   |   |    |   |   |   |     '---+            '-+         +
 1   2 3   4    1   2   3   4    1   2   3   4         '--- 4          '-- 4     \ 4
```

