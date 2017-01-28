# MdTree #


Convert markdown to html with TOC(table of contents) tree. [https://github.com/menduo/mdtree](https://github.com/menduo/mdtree)

# Screenshot

![https://raw.githubusercontent.com/menduo/mdtree/master/assets/screenshots/mdtree-screenshot.png](https://github.com/menduo/mdtree)

# Install

```bash
pip install mdtree
```

# Usage

## In Python
```python
from mdtree import MdTree
with open(path_of_md_file) as f:
    md_str = f.read()

mt = MdTree()
html = mt.convert(md_str)
fpath = mt.save_file("/tmp/mdtree.html")

mt = MdTree()
html = mt.convert_file("/tmp/gitit_bigger_readme.md")
```

## In Shell

```bash
mdtree /path/of/markdown/file.md > /tmp/mdtree.html
```

# Meta

mdtree allows you to add more things to the html file:

- css
- js
- title

```markdown
---
title: 这是一个标题
js:
    https://raw.githubusercontent.com/menduo/mdtree/master/static/js/mdtree.min.js
    https://raw.githubusercontent.com/menduo/mdtree/master/static/js/mdtree2.min.js
css:
    https://raw.githubusercontent.com/menduo/mdtree/master/static/css/mdtree.min.css
    https://raw.githubusercontent.com/menduo/mdtree/master/static/css/mdtree2.min.css
---
```

# Markdown Extensions

By default, these extensions were enabled. You can add more extensions or disable them.

```python
_md_extensions = [
    "markdown.extensions.meta",
    "markdown.extensions.headerid",
    "markdown.extensions.tables",
    "markdown.extensions.toc",
    "markdown.extensions.fenced_code",
    "markdown.extensions.codehilite",
]
```

You can customize them in the `meta` section:

```markdown
---
title: 这是一个标题
js:
    https://raw.githubusercontent.com/menduo/mdtree/master/static/js/mdtree.min.js
css:
    https://raw.githubusercontent.com/menduo/mdtree/master/static/css/mdtree.min.css
exts:
    markdown.extensions.wikilinks
    -markdown.extensions.codehilite
---
```

As you know, `markdown.extensions.wikilinks` will be added, and `-markdown.extensions.codehilite` which starts with `-` will be removed.

The name of the extensioins should be the same as [https://pythonhosted.org/Markdown/extensions/#officially-supported-extensions](https://pythonhosted.org/Markdown/extensions/#officially-supported-extensions)


# Credits
- [Markdown](https://github.com/waylan/Python-Markdown) - A Python implementation of John Gruber’s Markdown
- [i5ting_ztree_toc](https://github.com/i5ting/i5ting_ztree_toc) - a jQuery plugin for preview markdown table of content jQuery