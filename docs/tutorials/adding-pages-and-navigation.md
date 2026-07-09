# Adding pages and navigation

This tutorial shows you how to add new pages to your site and organize them into a structured navigation menu.

## Create new pages

First, create a few new Markdown files inside your `docs` directory. For better organization, it's a good practice to group related pages into sub-folders.

Create a new folder `docs/features` and add two files:

`docs/features/search.md`:
```markdown
# Search

Our documentation has built-in search.
```

`docs/features/themes.md`:
```markdown
# Themes

We use the Material for MkDocs theme.
```

Your project structure should now look like this:
```text
my-project/
├─ docs/
│  ├─ features/
│  │  ├─ search.md
│  │  └─ themes.md
│  └─ index.md
└─ mkdocs.yml
```

If your `mkdocs serve` process is still running, you will notice that these new pages are not yet visible in the site's navigation.

## Configure the navigation

To add the new pages to your site's navigation, you need to edit the `nav` section in your `mkdocs.yml` file.

Open `mkdocs.yml` and add the `nav` configuration:

```yaml title="mkdocs.yml"
site_name: My Docs
nav:
  - Home: index.md
  - Features:
    - Search: features/search.md
    - Themes: features/themes.md
```

### Functionality

The top-level key `nav` tells MkDocs the structure of the navigation on the left side. With `Home: index.md`, it creates a top-level link named "Home" that points to `index.md`. `Features` will create a top-level navigation section, which has two subpages: `Search` and `Themes` with their own respective paths to markdown files.

!!! success "Expected result"
    Your site now has a "Features" dropdown menu in the navigation bar, containing links to your "Search" and "Themes" pages.

---

You have now learned how to expand your site with new pages and control their order and structure in the navigation.
