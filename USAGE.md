# Usage
Halcyon is a clean and simple personal site/blog theme for Zola.

## Table of Contents
- [Installation](#installation)
- [Configuration](#configuration)
- [Content Structure](#content-structure)
- [Features](#features)
- [Customization](#customization)
- [Directory Structure](#directory-structure)
- [Tips](#tips)

## Installation

### As a Git Submodule
```bash
git submodule add https://github.com/m0ddr/halcyon themes/halcyon
```

### Direct Download
Alternatively you can clone the repository directly your `themes/` directory.

## Configuration
Set the theme in your `config.toml`:

```toml
theme = "halcyon"
```

### Basic Configuration
```toml
base_url = "https://your-site.com"
title = "Your Site Title"
description = "Your site description"
author = "Your Name"

compile_sass = true
build_search_index = false

taxonomies = [
    { name = "tags" },
]

generate_feeds = true
feed_filenames = ["atom.xml"]

[markdown]
highlight_code = true
highlight_theme = "boron"
bottom_footnotes = true

[extra]
links = [
    { title = "github", href = "https://github.com/yourusername" },
    { title = "email", href = "mailto:you@example.com" },
]
```

## Content Structure

### Homepage
Create `content/_index.md`:

```markdown
+++
[extra]
bio = "Your bio description"
username = "yourusername"
avatar = "path/to/avatar.jpg"  # optional
+++

Your homepage content goes here.
```

### Blog Posts
Create posts in `content/posts/`:

```markdown
+++
title = "Post Title"
date = 2024-01-01
description = "Post description"
taxonomies.tags = ["tag1", "tag2"]

[extra]
math = true  # optional, enables KaTeX
+++

Your post content.
```

### Custom Pages
Create pages with navigation links:

```markdown
+++
title = "Projects"
extra.in_header = true  # adds to navigation
+++

Page content.
```

## Features

### Dark/Light Mode
The theme includes automatic dark/light mode toggle buttons. Theme preference is saved in session storage.

### Code Blocks
Code blocks automatically include copy buttons. All major languages are supported with syntax highlighting.

### Math Support
Enable math rendering in posts:

```markdown
+++
[extra]
math = true
+++

Inline math: $f(x) = x^2$

Block math:
$$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$$
```

### Shortcodes

#### GitHub Repository
Display repository information:

```markdown
{{ gh_repo(owner="rust-lang", repo="rust") }}
```

#### YouTube Videos
Embed YouTube videos:

```markdown
{{ youtube(id="VIDEO_ID") }}
```

### Tags
Posts can be tagged using the taxonomies system:

```markdown
+++
taxonomies.tags = ["rust", "programming", "tutorial"]
+++
```

Tag pages are automatically generated at `/tags/`.

### RSS/Atom Feeds
Feeds are automatically generated when `generate_feeds = true` is set.

## Customization

### Styling
The theme uses CSS custom properties for colors. Override them by modifying `sass/_theme.scss` or adding custom CSS.

### Navigation
Add custom links to the header navigation:

```toml
[extra]
links = [
    { title = "portfolio", href = "/portfolio" },
    { title = "contact", href = "/contact" },
]
```

### Avatar
Add an avatar to your homepage by setting the `avatar` field in `content/_index.md`:

```markdown
+++
[extra]
avatar = "/images/avatar.jpg"
+++
```

## Directory Structure
```
content/
├── _index.md          # Homepage
├── posts/
│   ├── _index.md      # Posts section page
│   └── post-name.md   # Individual posts
└── projects.md        # Custom pages

static/
├── images/            # Images
└── ...               # Other static files

templates/             # Theme templates (don't modify)
sass/                  # Theme styles (customizable)
```

## Tips
- Use descriptive filenames for posts (they become URL slugs)
- Keep image sizes reasonable for faster loading