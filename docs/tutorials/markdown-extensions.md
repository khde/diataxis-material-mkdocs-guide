# Markdown extensions

This tutorial explains how to use some of Material for MkDocs most useful Markdown extensions to make your content more readable and interactive. You will learn how to add admonitions, styled code blocks, content tabs, and collapsible blocks.

## Prerequisites

To use these extensions, enable the corresponding Markdown extensions in your `mkdocs.yml` file. Make sure your `markdown_extensions` section looks like this:

```yaml title="mkdocs.yml"
markdown_extensions:
  - admonition
  - pymdownx.details
    - pymdownx.superfences:
            custom_fences:
                - name: mermaid
                    class: mermaid
                    format: !!python/name:pymdownx.superfences.fence_code_format
  - pymdownx.tabbed:
      alternate_style: true
```

## Admonitions

Admonitions are styled call-out blocks that are perfect for notes, warnings, or tips.

### How to use them

Create an admonition by using `!!!` followed by a type qualifier.

```markdown
!!! note
    This is a note.

!!! warning "Don't forget"
    This is a warning.
```

Example:

!!! tip "Quick fix"
    This is a tip.


### Types of admonitions

- `note`
- `info`
- `tip`
- `question`
- `warning`
- `danger`
- `bug`
- `example`

## Code blocks

You can add syntax highlighting and titles to your code blocks.

### How to use them

To enable syntax highlighting, add the language identifier after the opening backticks. To add a title, use `title="Your Title"` after the language.

```markdown
```python title="my_script.py"
import os

def main():
    print("Hello, world!")

if __name__ == "__main__":
    main()
```

Example:

```python title="my_script.py"
import os

def main():
    print("Hello, world!")

if __name__ == "__main__":
    main()
```

## Content tabs

Content tabs are useful for grouping related but distinct information, such as installation instructions for different operating systems.

### How to use them

Use `=== "Tab Title"` to create each tab.

```markdown
=== "Linux / macOS"
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

=== "Windows"
    ```powershell
    python.exe -m venv .venv
    .venv\Scripts\activate
    ```
```

Example:

=== "Linux / macOS"
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

=== "Windows"
    ```powershell
    python.exe -m venv .venv
    .venv\Scripts\activate
    ```

## Collapsible blocks

You can hide less critical or lengthy content inside collapsible blocks, similar to admonitions.

### How to use them

Use `???` for a block that is closed by default or `???+` for a block that is open by default.

```markdown
??? note "Click to expand"
    This content is hidden by default. It's useful for supplementary information or long log outputs.

???+ tip "This one is open"
    This content is visible by default but can be collapsed by the user.
```

Example:

??? info "Build log (collapsed)"
    ```text
    INFO   Building documentation...
    DEBUG  Reading file: docs/index.md
    ERROR  Missing reference: api/usage.md
    ```

---

You can now use these extensions to create richer and more user-friendly documentation pages.

## Mermaid diagrams

Mermaid diagrams are useful for visualizing processes, flows, and relationships directly in Markdown. In Material for MkDocs, they are enabled with a custom Superfences block.

### How to use them

Add the Mermaid fence to your `mkdocs.yml` file:

```yaml title="mkdocs.yml"
markdown_extensions:
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_code_format
```

Example:

``` mermaid
sequenceDiagram
    participant Client
    participant Server
    Client->>Server: POST /api/auth/login (username, password)
    Note over Server: Validate credentials
    Server-->>Client: 200 OK (Issuing JWT)
    Note over Client: Store token
    Client->>Server: GET /api/user with header Authorization: Bearer <token>
    Note over Server: Verify Signature & Expiration
    Server-->>Client: 200 OK (Data)
```
