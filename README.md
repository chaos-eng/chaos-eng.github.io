# Principles of Chaos Engineering

We use [hugo] to generate the HTML, which means you need it installed.

This repo also uses submodules, so be sure to do:

```bash
git submodule init
git submodule update
```

## Test out your changes

```
hugo server -D
```

## Generate source files and add them to git

```
hugo
git add docs
```


Static site, based on slightly  modified [hugo-theme-pixyll](https://github.com/azmelanar/hugo-theme-pixyll).
Theme used: [hugo-theme-pixyll](https://github.com/DenisBalan/hugo-theme-pixyll)

[hugo]: https://gohugo.io/getting-started/