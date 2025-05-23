+++
date = '2025-05-16T19:31:36-04:00'
draft = false
title = 'Hello World + Style'
slug = 'hello-world'
categories = 'blog'
toc = true
description = 'So this is a description'
+++
# Hello World
## Hugo is a markdown-first static site generator.
I guess the TOC doesn't detect top level headers
### but what happens when there are more headers?
that's my question
#### and there's one way to find out
by making a ton of them.
I want to see what the line settings loook like
it doesn't look like partials is doing anything so idk.

## Syntax
I'm just trying to see how the TOC works now

## Header 3
because I've seen some varieties have numbers on them instead of bullet points

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
:   definitions can contain multiple paragraphs. But I think you have to 
    remember to put a space between the term and the definition so that 
    the renderer wraps the definition paragraph in p tags.

    1. lists
    2. are supposed to work

    >blockquotes
    > too

    Definitions render inside of dl tags. I customized the css to center text 
    in main articles. I made a few exceptions -- one of which is that text inside of a dl tag is left-justified. 
    This is to preserve the format of the dictionary entries.

## Tables
I want to see how they render

| Italics   | Bold     | Code   |
| --------- | -------- | ------ |
| _italics_ | **bold** | `code` |

alright that's different from what I'm used to.
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

