# .dot files

The files in this directory represent graphs in the [GraphViz](https://graphviz.gitlab.io/)
[DOT](https://graphviz.gitlab.io/_pages/doc/info/lang.html) language.

## Rendering

To render a `.dot` file to PDF, PNG, or one of the `dot` command’s [many supported formats](https://graphviz.gitlab.io/_pages/doc/info/output.html):

```
$ dot -T[FORMAT] [INPUT-FILE] > [OUTPUT-FILE]
```

E.g.

```
$ dot -Tpdf cursive.dot > cursive.pdf
```

### Output size

To render a `.dot` file as a PNG scaled to (just) fit within a 1440×1440–pixel box:

```
$ dot -Tpng -Gsize=20,20\! -Gdpi=72 -o[OUTPUT-FILE] [INPUT-FILE]
```

| Argument | Meaning |
| --- | --- |
| `-Gsize=20,20\!` | 20"×20" image; `!` = desired size (i.e., scale up to fit) |
| `-Gdpi=72` | 72 dpi |

Source: https://stackoverflow.com/a/20536144/27358

### Multi-page PDFs

To render a multi-graph file to a multiple-page PDF:

```
$ dot -Tps2 [INPUT-FILE] -o [OUTFILE].ps | ps2pdf [OUTFILE].ps [OUTFILE].pdf
```
