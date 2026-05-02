# YAML configuration

## Reference configuration

```yaml
site_name: Your Project Docs # (1)
site_description: My description here # (2)
site_url: https://<your-user>.github.io/<your-repo>/ # (3)
repo_url: https://github.com/<your-user>/<your-repo>/ # (4)
edit_uri: edit/main/docs/ # (5)

docs_dir: docs # (6)

nav:
  - Home: index.md # (7)
  - Getting started:
      - getting-started/index.md # (8)
      - Installation: getting-started/installation.md
      - Usage: getting-started/usage.md
  - About: about.md

theme:
  name: material # (9)
  icon:
    repo: fontawesome/brands/github # (10)
    logo: material/book-open-page-variant # (11)

  features:
    - content.action.view # (12)
    - content.code.copy # (13)
    - content.code.annotate # (14)
    - navigation.footer # (15)
    - navigation.top # (16)
    - navigation.indexes # (17)
    - navigation.tabs # (18)
    - navigation.tabs.sticky # (19)
    - search.suggest # (20)
    - search.highlight # (21)
    - search.share # (22)

  palette:
    - media: "(prefers-color-scheme: light)" # (23)
      scheme: default
      primary: white
      accent: blue
      toggle:
        icon: material/weather-night
        name: Dark mode
    - media: "(prefers-color-scheme: dark)" # (24)
      scheme: slate
      primary: black
      accent: blue
      toggle:
        icon: material/weather-sunny
        name: Light mode
  
  font:
    text: Inter # (25)
    code: Google Sans Code # (26)

markdown_extensions:
  - admonition # (27)
  - attr_list # (28)
  - md_in_html # (29)
  - pymdownx.details # (30)
  - pymdownx.superfences # (31)

plugins:
  - search # (32)

extra:
  generator: false # (33)
```

1.  `site_name`: Sets the site's main title, appearing in the header and browser tab.
2.  `site_description`: Provides a brief summary for search engine results and metadata.
3.  `site_url`: Defines the canonical public URL for the site.
4.  `repo_url`: Links to the source code repository, often displayed as an icon.
5.  `edit_uri`: Constructs the "Edit this page" link for each page.
6.  `docs_dir`: Specifies the directory containing the Markdown source files.
7.  `nav`: Defines the site's navigation structure and page order.
8.  Section `index.md` pages serve as stable, linkable landing pages for navigation sections.
9.  `theme.name`: Specifies the theme to use for the site's appearance.
10. `theme.icon.repo`: Sets the icon for the repository link.
11. `theme.icon.logo`: Sets the site's logo icon, displayed in the header.
12. `features.content.action.view`: Adds a button to view the source of the current page.
13. `features.content.code.copy`: Adds a copy button to all code blocks.
14. `features.content.code.annotate`: Enables code annotations for explaining code snippets.
15. `features.navigation.footer`: Adds previous/next page links in the footer.
16. `features.navigation.top`: Adds a "back to top" button.
17. `features.navigation.indexes`: Makes section index pages act as landing pages in the navigation.
18. `features.navigation.tabs`: Renders top-level navigation items as tabs.
19. `features.navigation.tabs.sticky`: Makes the navigation tabs stick to the top of the viewport.
20. `features.search.suggest`: Provides search query auto-completion.
21. `features.search.highlight`: Highlights search terms on result pages.
22. `features.search.share`: Adds a button to share a search query.
23. `palette` (light): Defines the color scheme for light mode.
24. `palette` (dark): Defines the color scheme for dark mode.
25. `font.text`: Sets the main font for body text.
26. `font.code`: Sets the font for code blocks.
27. `markdown_extensions.admonition`: Enables styled blocks for notes, warnings, and tips.
28. `markdown_extensions.attr_list`: Allows adding HTML attributes to Markdown elements.
29. `markdown_extensions.md_in_html`: Allows processing Markdown syntax inside HTML blocks.
30. `markdown_extensions.pymdownx.details`: Enables collapsible content blocks.
31. `markdown_extensions.pymdownx.superfences`: Enables nesting code blocks and other advanced features.
32. `plugins.search`: Enables the built-in search functionality.
33. `extra.generator`: Hides the "Made with Material for MkDocs" notice in the footer.
