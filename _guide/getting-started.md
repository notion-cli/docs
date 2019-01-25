---
title: Getting Started
---

# Getting Started

## Unix Installation

On most Unix systems, you can install Notion with a single command:

```bash
curl -sSLf https://get.notionjs.com | bash
```

For [bash](https://www.gnu.org/software/bash/), this installer will automatically update your console startup script.

{% include warn.html content="The installation script is currently tailored to bash. A more universal installer is in development, but Notion should work in all shells." %}

To configure other shells to use Notion, edit your console startup scripts to:
- Set the `NOTION_HOME` variable to `~/.notion`
- Add `$NOTION_HOME/bin` to the beginning of your `PATH` variable

## Windows Installation

{% include warn.html content="A Windows installer is in development." %}
