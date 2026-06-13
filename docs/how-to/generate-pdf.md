# Generate a PDF file out of MkDocs
This page describes how to generate a PDF file from the MkDocs documentation using mkdocs-exporter.

## PDF Export from MkDocs

MkDocs does not natively support PDF generation. However, the MkDocs plugins provides several solutions to export the documentation as a PDF. Popular plugins include `mkdocs-pdf-export-plugin` and `mkdocs-with-pdf`, However this how-to focuses on `mkdocs-exporter`.

### Installing mkdocs-exporter

First, install the mkdocs-exporter package using pip:

```bash
pip install mkdocs-exporter
```

Additionally, Playwright needs to install browser binaries that it uses to render pages. Run the following to install those browsers:

```bash
playwright install
```

### Configuring mkdocs-exporter

Add the plugin to the `mkdocs.yml` configuration file with the basic settings:

```yaml
plugins:
  - exporter:
      formats:
        pdf:
          enabled: true
          concurrency: 8
```

The `concurrency` setting controls how many pages are rendered in parallel, speeding up the PDF generation process.

### Aggregating into a Single PDF

By default, the exporter generates individual PDF files for each page. To combine all pages into a single PDF document, enable the aggregator option:

```yaml hl_lines="7 8 9 10"
plugins:
  - exporter:
      formats:
        pdf:
          enabled: true
          concurrency: 8
          aggregator:
            enabled: true
            covers: all
            output: output.pdf
```

### Generating the PDF

After configuration, generate the PDF by running:

```bash
mkdocs build
```

For the configured aggregation, the combined PDF will be located at `site/output.pdf`.
Individual page PDFs are also generated and placed in the same `site/` directory alongside the static HTML files.