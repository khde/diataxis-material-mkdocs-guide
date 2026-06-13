# Implementing a Dark/Light Mode Toggle
This page describes how to add a dark and light mode toggle to Material for MkDocs documentation.

## Color Scheme Preferences

Material for MkDocs supports multiple color schemes, allowing users to choose between light and dark modes based on their preference. The schemes can be configured to automatically use the users system preference while providing a manual toggle to switch between them.

## Setting up the Color Scheme Toggle

To add a dark and light mode toggle to the site, configure the `palette` section in `mkdocs.yml` file. This section defines the available color schemes and how users can switch between them.

### Basic Configuration

Add the palette configuration to the `theme` section in `mkdocs.yml`:

```yaml
theme:
  name: material
  
  palette:
    - media: "(prefers-color-scheme: light)"
      scheme: default
      primary: white
      accent: blue
      toggle:
        icon: material/weather-night
        name: Dark mode
    - media: "(prefers-color-scheme: dark)"
      scheme: slate
      primary: black
      accent: blue
      toggle:
        icon: material/weather-sunny
        name: Light mode
```