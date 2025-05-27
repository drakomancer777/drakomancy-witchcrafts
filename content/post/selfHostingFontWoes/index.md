+++
date = '2025-05-27T15:23:52-04:00'
draft = false
title = 'Self-Hosting a Google Font on Hugo'
slug = 'self-hosting-a-Google-font-on-hugo'
categories = 'blog'
tags = ['hugo']
toc = true
description = 'I decided to self-host the font, but since I am me, there were ...complications.'
+++

TL;DR: I have once again been defeated by directory paths
<!--more-->

# Self-Hosting a Google Font on Hugo 
## Why Self-Host
Self-Hosting fonts can lessen dependency on CDNs and plays nicely with EU GDPR. 
As a big fan of data privacy (though, I've yet to iron out some lingering issues built-in this theme), 
I decided I wanted to load my font for this blog from its own directory rather than loading it from Google. 
## The Simple Process
It's actually *exceedingly* simple. Especially with tools like [https://gwfh.mranftl.com/fonts](https://gwfh.mranftl.com/fonts) 
that streamline multiple steps for you. 
1. Find the desired font at [https://fonts.google.com/](https://fonts.google.com/)
2. *HIGHLY* recommend [https://gwfh.mranftl.com/fonts](https://gwfh.mranftl.com/fonts) to download the WOFF2 files. Google fonts are free to download, but Google only provides the outdated TTF format. So save the hassle. Just use this tool, otherwise the TTF will need to be converted anyway by some other fool service that christens it with an *ugly* file name on completion.
3. Make a directory named "fonts" in the static directory
4. Unzip the font files directly into static/fonts
   - OR, if using multiple *different* fonts, makes sense to make directories for each different font within the /fonts directory

```goat
root
 └─ static
    └─ fonts
       ├─ montserrat      
       │  ├─ montserrat_regular.woff2
       │  └─ montserrat_italic.woff2
       └─ roboto
          ├─ roboto_regular.woff2
          └─ roboto_regular.woff2
```

5. Copy the given CSS from [https://gwfh.mranftl.com/fonts](https://gwfh.mranftl.com/fonts) and paste it into a css file in the project.
   - Unfortunately, themes can complicate this issue. More on that below.
   - You can absolutely write your own `@font-face` blocks.
   - You can also use the snips Google provides, but the CSS provided by gwfh is just better.
   - The CSS for this will be something like:
```css
/* atkinson-hyperlegible-next-200 - latin-ext */
@font-face {
  font-display: swap; /* Check https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display for other options. */
  font-family: 'Atkinson Hyperlegible Next';
  font-style: normal;
  font-weight: 200;
  src: url('../fonts/atkinson-hyperlegible-next-v4-latin-ext-200.woff2') format('woff2'), /* Chrome 36+, Opera 23+, Firefox 39+, Safari 12+, iOS 10+ */
  url('../fonts/atkinson-hyperlegible-next-v4-latin-ext-200.ttf') format('truetype'); /* Chrome 4+, Firefox 3.5+, IE 9+, Safari 3.1+, iOS 4.2+, Android Browser 2.2+ */
}
```
6. Implement the new font in CSS styles the way you would a "web-safe font".
   - Some people do seem to forget this step.
## Struggles + Pitfalls Witnessed While Troubleshooting
1. **Confusion about directory path.**
This is the one that got me. 
Common advice dictates that the source url in the `@font-face` declaration should follow the format of `'/fonts/<rest of path...>'` 
but this was part of why it wasn't working for me. It didn't suit my directory structure. 
I actually needed to disregard the common advice and do some more directory navigation in the source url to get it to work. 
2. **Caching**. Some people think it isn't working when it's really a caching issue. 
3. **Syntax errors**. Within the `@font-face` declaration. That's why tools like gwfh are so nice to have.
4. **Theme Conflict**. Some themes have their own options for customizing fonts. Or sometimes the way the themes load fonts 
can inadvertently cause issues for a user trying to implement a different font. My theme didn't have any inherent complications 
with changing the font, but some themes are built for you to take different steps to change the font. A good theme 
will have those steps outlined in the theme's documentation. If not, it's possible to find a discussion with the solution by 
looking in the discussion for the theme's repository or by starting a discussion there. 

## Atkinson Hyperlegible Next (My Font)
The font I'm using is called **Atkinson Hyperlegible Next**.
It is a free font designed for accessibility and ease of reading for visually impaired people. 
It's an improvement over Atkinson Hyperlegible. There's a monospaced version too! 
[https://en.wikipedia.org/wiki/Atkinson_Hyperlegible](https://en.wikipedia.org/wiki/Atkinson_Hyperlegible)






