# Getting started

## Prerequisites

- Python 3.8+
- `pip`

!!! note "Optional: Create a virtual environment"
    It is recommended to create a virtual environment.

    === "Linux"

        ```bash
        python3 -m venv .venv
        source .venv/bin/activate
        ```
    === "Windows"

        ```powershell
        python.exe -m venv .venv
        .venv\Scripts\activate
        ```

    === "macOS"

        ```bash
        python3 -m venv .venv
        source .venv/bin/activate
        ```

## Step 1: Install Material for MkDocs

Material for MkDocs can be installed using `pip`.

```bash
pip install mkdocs-material
```

Check the installation:

```bash
mkdocs --version
```

!!! bug

    The latest version of MkDocs has a bug that is prevents auto-reloading, see [issue](https://github.com/mkdocs/mkdocs/issues/4032).

    This can be solved by installing an older click version:
    ```bash
    pip install click==8.2.1
    ```

## Step 2: Create a new project

```bash
mkdocs new my-project
cd my-project
```

Your folder now contains:

```text
my-project/
├─ docs/
│  └─ index.md
└─ mkdocs.yml
```

## Step 3: Start the local server

```bash
mkdocs serve
```

Open `http://127.0.0.1:8000` in your browser.

!!! success "Expected result"
    You should see a simple documentation site with a single home page.

## Step 4: Edit your first page

Open `docs/index.md` and replace the content:

```markdown title="docs/index.md"
# Hello MkDocs

This page is live-reloaded while the server runs.
```

Now refresh your browser.

!!! tip "What to notice"
    The page updates immediately because MkDocs watches your files.

## Step 5: Build static output

In a second terminal, run:

```bash
mkdocs build
```

This creates a `site/` directory containing static HTML/CSS/JS.

---

You have built your first documentation site.
