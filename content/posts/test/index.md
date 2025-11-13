+++
title = "Test Post"
date = 2025-07-29
taxonomies.tags = ["test"]

[extra]
math = true
+++

This is just a quick and dirty test
## Math
Maths is rendered by KaTex

Inline math: $f(a,b,c) = (a^2+b^2+c^2)^3$

**Block math:**
$$f(a,b,c) = (a^2+b^2+c^2)^3$$

If you wanted to use maths you need to ensure it's enabled when writing the post:
```yaml
[extra]
maths = true
```
This will call the KaTex auto-render extension CDN and math contained in the following tags will be rendered accordingly:

```
$math$ for inline math
$$math$$ for display math
```

## Images
Images should be pretty self explainitory, for personal preference I've set images to center themselves subject to size on the page

{{figure(src="images/1.jpg", alt="Example image", caption="Example caption demonstrating figure captions")}}

Usage:
```markdown
{figure(src="images/example.jpg", alt="Description", caption="Example caption")} # With caption (double curly brackets)
{figure(src="images/example.jpg", alt="Description")} # Without caption (double curly brackets)
```

## Github Repos
Lastly the only other shortcode I've implimented is github repos:

**Rust:**
{{gh_repo(owner="rust-lang", repo="rust")}}

Usage:
```markdown
{gh_repo(owner="rust-lang", repo="rust")} # This would be double curly brackets
```
