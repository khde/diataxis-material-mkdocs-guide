# Configuring your site

This tutorial explains how to configure your project by editing the `mkdocs.yml` file. You will learn how to set basic site information, apply the Material for MkDocs theme, and enable some of its key features.

## Set basic site information

Let's configure the site by setting these core options in `mkdocs.yml`. Update your file to look like this:

```yaml title="mkdocs.yml"
site_name: My Docs
site_url: https://example.com/
site_description: A short description of my documentation site.
repo_url: https://github.com/your-username/your-repo

nav:
  - Home: index.md
```

-   `site_name`: The title of your documentation site.
-   `site_url`: The full public URL where your site will be hosted.
-   `site_description`: A short summary used for search engine results and metadata.
-   `repo_url`: The URL of your source code repository (e.g., GitHub, GitLab).

## Apply the Material for MkDocs theme

Now, let's switch from the default theme to Material for MkDocs.

Add the `theme` section to your `mkdocs.yml`:

```yaml title="mkdocs.yml"
site_name: My Docs
# ... (other settings)

theme:
  name: material
```

!!! success "Expected result"
    If `mkdocs serve` is running, your site will automatically reload with a new dark look. You are now using the Material for MkDocs theme.

## Enable theme features

Material for MkDocs includes many features that can be enabled under the `theme.features` key. Here we will enable some features.

Update your `theme` configuration:

```yaml title="mkdocs.yml"
# ... (other settings)

theme:
  name: material
  features:
    - navigation.tabs
    - navigation.footer
    - navigation.top
```

-   `navigation.tabs`: Turns the top-level navigation into tabs.
-   `navigation.footer`: Adds "Previous" and "Next" page links in the footer.
-   `navigation.top`: Adds a "Back to top" button that appears when you scroll down.

## Enable and configure search

Search is a built-in plugin that is enabled by default. However, as soon as you add the `plugins` key to your configuration, you must explicitly include `search` to keep it.

Add the `plugins` section to your `mkdocs.yml`:

```yaml title="mkdocs.yml"
# ... (other settings)

plugins:
  - search:
```

-   `plugins`: The list of plugins to enable.

## Change the color palette

You can easily change the site's colors using the `palette` option.

Update your `theme` configuration again:

```yaml title="mkdocs.yml" hl_lines="9 10 11"
# ... (other settings)

theme:
  name: material
  features:
    - navigation.tabs
    - navigation.footer
    - navigation.top
  palette:
    scheme: slate
    primary: blue

plugins:
  - search:
```

-   `scheme: slate`: Switches the site to a dark mode theme.
-   `primary: blue`: Sets the primary accent color to blue.

---

You have now learned the basics of configuring your site, applying a theme, and customizing its features and appearance.
