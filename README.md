# Portfolio

My site: https://upura.github.io/
Forked from: https://github.com/sourcethemes/academic-kickstart

## Requirements

- Hugo extended `0.161+`

## Local development

```bash
sh view.sh
```

## How to deploy

```bash
sh deploy.sh
```

## Caveats

The `themes/academic` submodule is pinned to a local commit that is **not pushed to `origin` (gcushen/hugo-academic)**. The local commit migrates the theme away from `site.LanguageCode` / `site.Data` (deprecated in Hugo 0.158 / 0.156) so the site builds cleanly on Hugo 0.161+. A fresh `git clone` followed by `git submodule update --init` will fail to fetch this commit. If working on a new machine, either:

- copy the `themes/academic/` directory from a working checkout, or
- push the submodule commit to a personal fork and update `.gitmodules` to point there.
