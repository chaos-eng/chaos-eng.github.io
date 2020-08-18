# Principles of Chaos Engineering

This is the source for [principlesofchaos.org](https://principlesofchaos.org).

It's a static site, generated with [hugo].

Theme used:
[DenisBalan/hugo-theme-pixyll](https://github.com/DenisBalan/hugo-theme-pixyll)
(a slightly modified version of [hugo-theme-pixyll](https://github.com/azmelanar/hugo-theme-pixyll))

[hugo]: https://gohugo.io/getting-started/


## Prereqs

* Install [hugo] so you can generate the html
* Check out the submodule that contains a Hugo theme:

```bash
git submodule init
git submodule update
```

## Add a translation in a new language

1. Identify the [ISO 639-1 two-letter code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for your language (e.g., `pl` for Polish).
1. Create a `content/_index.xx.md` file (where `xx` is the two-letter country code), and populate it with the text.
1. Edit the [config.toml](config.toml) file and add a `[Languages.xx]` line under the `[Languages]` section
1. To test locally: `hugo server -D`
1. To generate the html files: `hugo`
1. Commit all of the generated files: `git add config.toml && git add docs`
