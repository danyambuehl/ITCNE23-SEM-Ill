---
layout: default
title: Just the Docs
parent: Configuration
#grand_parent: Einleitung
nav_order: 3
---

## Inhaltsverzeichnis
{: .no_toc .text-delta }

1. TOC
{:toc}

## Just the Docs [^1] [^4]

Just the Docs ist ein theme für die Erstellung statischer Websites mit Jekyll. 
Die Dokumentation kann ganz einfach in Markdown oder HTML geschrieben werden.
Jekyll erstellt aus der Dokumentation eine Website, indem es alle Dateien, in HTML konvertiert. 
Das Design kann mit der Jekyll-Konfigurationsdatei bestimmt werden zu verwendende Thema und legt allgemeine Parameter für Ihre Website fest.

Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages.

### Voraussetzungen

Folgende Files müssen erstellt werden:

| File                  | Description                 |
| ---                   | ---                         |
| _config.yml           | Jekyll Konfiguration File   |
| index.md              | Hauptseite                  |
| .github\pages.yaml    | Pipeline Konfiguration File  |

### Konfiguration von GitHub Pages

Unter Einstellungen, muss GitHub Pages auf dem entsprechenden Branch aktiviert werden.

![Banner](../img/activate.png)

### Konfiguration von GitHub Actions [^2]

Erstelle ein neues File mit dem Namen .github\pages.yaml und fügen Sie den folgenden Inhalt ein:
Dieses File ist für die Pipeline verantwortlich. Sobald Änderungen im Repository vorgenommen werden, wird die Pipeline automatisch gestartet und die Webseite aktualisiert.

```yaml
# Sample workflow for building and deploying a Jekyll site to GitHub Pages
name: Deploy Jekyll site to Pages

on:
  push:
    branches: ["pages"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow one concurrent deployment
concurrency:
  group: "pages"
  cancel-in-progress: true

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.1' # Not needed with a .ruby-version file
          bundler-cache: true # runs 'bundle install' and caches installed gems automatically
          cache-version: 0 # Increment this number if you need to re-download cached gems
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v2
      - name: Build with Jekyll
        # Outputs to the './_site' directory by default
        run: bundle exec jekyll build --baseurl "${{ steps.pages.outputs.base_path }}"
        env:
          JEKYLL_ENV: production
      - name: Upload artifact
        # Automatically uploads an artifact from the './_site' directory by default
        uses: actions/upload-pages-artifact@v1

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v1
```

### Konfiguration von Jekyll [^3] [^6]

Erstelle ein neues File mit dem Namen _config.yml und fügen Sie den folgenden Inhalt ein:

```yaml
title: ITCNE23-SEM-ll
description: Automatisierungslösung 
remote_theme: just-the-docs/just-the-docs
#remote_theme: tomjoht/documentation-theme-jekyll
#remote_theme: dieghernan/chulapa

# Color scheme supports "light" (default) and "dark"
# color_scheme: dark

favicon_ico: "/docs/img/favorite.png"

url: https://danyambuehl.github.io/ITCNE23-SEM-ll

# Set a path/url to a logo that will be displayed instead of the title
logo: "/docs/img/logo.png"

# Aux links for the upper right navigation
aux_links:
  Projektplanung: https://github.com/users/danyambuehl/projects/2

# Makes Aux links open in a new tab. Default is false
aux_links_new_tab: true

footer_content: "Your Copyright Here  "

# For copy button on code
enable_copy_code_button: true

# Back to top link
back_to_top: true
back_to_top_text: "Back to top ⬆️"

# Footer last edited timestamp
last_edit_timestamp: true # show or hide edit time - page must have `last_modified_date` defined in the frontmatter
last_edit_time_format: "%b %e %Y at %I:%M %p" # uses ruby's time format: https://ruby-doc.org/stdlib-2.7.0/libdoc/time/rdoc/Time.htm

search_enabled: true
search:
  # Split pages into sections that can be searched individually
  # Supports 1 - 6, default: 2
  heading_level: 2
  # Maximum amount of previews per search result
  # Default: 3
  previews: 2
  # Maximum amount of words to display before a matched word in the preview
  # Default: 5
```

### Index.md File erstellen [^5]

Erstelle ein neues File mit dem Namen index.md und fügen Sie den folgenden Inhalt ein:
Dieses File ist für die Hauptseite verantwortlich.

```bash
---
layout: default                 # Layout of the page
title: Einleitung 
nav_order: 1                    # Order in the navigation bar
permalink: /    
has_children: true              # Enable the child pages
banner: /img/banner_2.png       # Banner image
has_toc: false                  # Disable Auto-generating Table of Contents
---
```

### Subpage erstellen

Um Ordnung zu halten habe ich für jede Kategorie ein eigenes Verzeichnis erstellt. /docs/02_Projekt/index.md
Hier ein beispiel für die Datei index.md
Dies ist die Hauptseite für die Kategorie Projekt, eine Subpage von Einleitung.

```bash
---
layout: default                 # Layout of the page
title: Projekt                  # Title of the page
nav_order: 2                    # Order in the navigation bar
parent: Einleitung              # Parent page in navigation
has_children: true              # Because its a parent page
---
```

### Pipeline

Jedes Mal, wenn Änderungen im Repository vorgenommen werden, wird die Pipeline automatisch gestartet und die Webseite aktualisiert.
Dies kann im Github Repository unter Actions verfolgt werden.

![Github Action](../img/github_actions.png)


## Quellen und Referenzen:

[^1]: Just the Docs Official (n.d.). [Retrieved from](https://just-the-docs.com/)
[^2]: Github Workflows. [Retrieved from](https://github.com/actions/starter-workflows/blob/main/README.md)
[^3]: Just the Docs Konfiguration Optionen (n.d.). [Retrieved from](https://github.com/just-the-docs/just-the-docs/blob/main/_config.yml)
[^4]: Jamstack Themes (n.d.). [Retrieved from](https://jamstackthemes.dev/#ssg=jekyll)
[^5]: Just the Docs Index (n.d.). [Retrieved from](https://github.com/just-the-docs/just-the-docs/blob/main/index.md)
[^6]: Customization (n.d.). [Retrieved from](https://just-the-docs.com/docs/customization/)
