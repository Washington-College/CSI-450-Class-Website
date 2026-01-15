# Quarto Quick Reference

Quick reference for common Quarto commands and syntax.

## 🔧 Terminal Commands

| Command | Description |
|---------|-------------|
| `quarto check` | Verify Quarto installation |
| `quarto preview` | Preview your site locally |
| `quarto render` | Build your website to `docs/` |
| `quarto render file.qmd` | Render a single file |
| `quarto --help` | Show all available commands |

## 📝 YAML Frontmatter

At the top of each `.qmd` file:

```yaml
---
title: "Your Title"
author: "Your Name"
date: "2026-01-15"
categories: [tag1, tag2]
format: html
---
```

## ✍️ Markdown Basics

```markdown
# Heading 1
## Heading 2
### Heading 3

**bold text**
*italic text*

[link text](https://example.com)

![image alt text](path/to/image.jpg)

- Bullet point 1
- Bullet point 2

1. Numbered item 1
2. Numbered item 2
```

## 💻 Code Blocks

### Python
````markdown
```{python}
#| echo: true
#| eval: true

import pandas as pd
df = pd.read_csv("data.csv")
print(df.head())
```
````

### R
````markdown
```{r}
#| echo: true
#| eval: true

library(ggplot2)
ggplot(mtcars, aes(x=wt, y=mpg)) + 
  geom_point()
```
````

### Code Options

| Option | Description | Values |
|--------|-------------|--------|
| `echo` | Show the code | `true`, `false` |
| `eval` | Run the code | `true`, `false` |
| `code-fold` | Collapsible code | `true`, `false` |
| `warning` | Show warnings | `true`, `false` |
| `message` | Show messages | `true`, `false` |

Example:
````markdown
```{python}
#| echo: true
#| eval: false
#| code-fold: true
#| warning: false

# Your code here
```
````

## 📊 Figures

```markdown
![Caption text](path/to/image.jpg){width=50%}

::: {#fig-label}
![Caption](image.jpg)

This is a figure with a caption and label.
:::
```

## 📦 Callout Boxes

```markdown
::: {.callout-note}
This is a note callout.
:::

::: {.callout-warning}
This is a warning callout.
:::

::: {.callout-tip}
This is a tip callout.
:::

::: {.callout-important}
This is an important callout.
:::
```

## 🔗 Cross-References

```markdown
See @fig-plot for the visualization.

Check out [Section 2](section-id).
```

## 📐 Math (KaTeX)

Inline math: `$E = mc^2$`

Display math:
```markdown
$$
f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}
$$
```

## 🌐 Useful Links

- [Full Quarto Documentation](https://quarto.org/docs/guide/)
- [Markdown Guide](https://quarto.org/docs/authoring/markdown-basics.html)
- [Code Blocks](https://quarto.org/docs/computations/execution-options.html)
- [Figures](https://quarto.org/docs/authoring/figures.html)
- [Website Options](https://quarto.org/docs/websites/)

## 🆘 Getting Help

```bash
# Get help on any command
quarto render --help
quarto preview --help

# Check Quarto version
quarto --version
```

---

📖 **Tip**: Keep this file open as a reference while working on your posts!
