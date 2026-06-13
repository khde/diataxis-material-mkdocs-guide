# Show information about a page

This page shows how to add page information to MkDocs site with two plugins: one for showing who edited a page and one for showing when it was last changed.

## Show who edited the page

Use [mkdocs-git-committers-plugin-2](https://github.com/ojacques/mkdocs-git-committers-plugin-2) to display the contributors who edited a page. The infomration will be displayed in the footer of the page.

Add the plugin to `mkdocs.yml` like this:

```yaml
plugins:
  - git-committers:
      repository: khde/diataxis-material-mkdocs-guide
      branch: master
      cache_dir: .cache/plugin/git-committers/
```

The plugin simply reads the Git history and shows the people who contributed to the page.

## Show when the page was last edited

Use [mkdocs-git-revision-date-localized-plugin](https://github.com/timvink/mkdocs-git-revision-date-localized-plugin) to show the last edit date on each page.

Add it to `mkdocs.yml` like this:

```yaml
plugins:
  - git-revision-date-localized:
      locale: en
      timezone: Europe/Amsterdam
      type: timeago
```