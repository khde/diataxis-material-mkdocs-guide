# Command reference

This page provides a quick reference to the main MkDocs commands.
For the complete set of options, refer to your local help output: `mkdocs --help` and `mkdocs <command> --help`.

## `mkdocs new`

Creates a new project directory with a minimal `mkdocs.yml` and a starter docs page.

```bash
mkdocs new my-project
```

## `mkdocs serve`

Runs a local development server and rebuilds the site on file change.

```bash
mkdocs serve
```

## `mkdocs build`

Builds the static site output (defaults to the `site/` directory).

```bash
mkdocs build
```

## `mkdocs gh-deploy`

Builds the site and publishes it to a Git branch, intended for GitHub Pages.

```bash
mkdocs gh-deploy
```

For a detailed how-to on publishing MkDocs sites to GitHub Pages, refer to this guide [here](../how-to/deploy-github-pages.md).
