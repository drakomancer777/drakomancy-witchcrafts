+++
date = '2025-05-18T22:38:50-04:00'
draft = false
title = 'Links'

[[links]]
title = "GitHub"
description = "GitHub is the world's largest software development platform."
website = "https://github.com"
image = "https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"
[[links]]
title = "TypeScript"
description = "TypeScript is a typed superset of JavaScript that compiles to plain JavaScript."
website = "https://www.typescriptlang.org"
image = "ts-logo-128.jpg"
[[links]]
title = "Catppuccin"
description = "Catppuccin is a community-driven color scheme for coding, designing, and much more!"
website = "https://catppuccin.com/"
image = "https://raw.githubusercontent.com/catppuccin/catppuccin/refs/heads/main/assets/logos/exports/1544x1544_circle.png"
[menu.main]
weight = 4
[menu.main.params]
icon = 'link'
comments = false
+++

To use this feature, add `links` section to frontmatter. <- boilerplate

This page's frontmatter in YAML:

```yaml
links:
  - title: GitHub
    description: GitHub is the world's largest software development platform.
    website: https://github.com
    image: https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png
  - title: TypeScript
    description: TypeScript is a typed superset of JavaScript that compiles to plain JavaScript.
    website: https://www.typescriptlang.org
    image: ts-logo-128.jpg
```

And now in TOML:
```toml
[[links]]
title = "GitHub"
description = "GitHub is the world's largest software development platform."
website = "https://github.com"
image = "https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"
[[links]]
title = "TypeScript"
description = "TypeScript is a typed superset of JavaScript that compiles to plain JavaScript."
website = "https://www.typescriptlang.org"
image = "ts-logo-128.jpg"
```

`image` field accepts both local and external images.

Big sorry for broken image lmao I'm going to need to place a TS logo in my directory at some point.
YAML to TOML converters have been so useful in this trying time. https://www.convertsimple.com/convert-yaml-to-toml/