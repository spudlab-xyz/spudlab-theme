# Spudlab Hugo theme

A restrained, accessible Hugo theme for open science, research, documentation, and community projects. It uses the [Spudlab brand palette](https://github.com/spudlab-xyz/.github/blob/main/docs/BRAND.md) by default, but its identity and content are configurable so other organisations can reuse it.

## Features

- Responsive homepage, section, article, taxonomy, and 404 layouts
- Automatic light/dark mode with a three-state theme control
- Keyboard navigation, skip link, visible focus states, reduced-motion support, and semantic landmarks
- Configurable brand name, logo, colours, navigation, social links, and homepage sections
- Project status, tags, reading time, table of contents, pagination, RSS, and social metadata
- No external fonts, JavaScript libraries, trackers, or build tools
- Example site showing the available page types

## Requirements

Hugo **0.123.0** or newer (extended or standard edition).

## Install

Add the theme to an existing Hugo site as a Git submodule:

```sh
git submodule add https://github.com/spudlab-xyz/spudlab-theme.git themes/spudlab-theme
```

Then set the theme in `hugo.yaml`:

```yaml
theme: spudlab-theme
```

You can also copy the repository into `themes/spudlab-theme` if you do not use submodules.

## Configuration

This is a complete starting configuration. Remove anything you do not need; all colour and most presentation settings have defaults.

```yaml
baseURL: https://example.org/
languageCode: en-gb
title: Your organisation
theme: spudlab-theme

menus:
  main:
    - name: Projects
      pageRef: /projects
      weight: 10
    - name: About
      pageRef: /about
      weight: 20
  footer:
    - name: Source code
      url: https://github.com/example

params:
  brandName: Your organisation
  description: A short site description used in metadata.
  author: Your organisation
  logo: images/logo.svg
  favicon: images/favicon.svg
  socialImage: images/social-card.png
  mainSections: [projects, posts]
  dateFormat: 2 January 2006
  showReadingTime: true
  showTableOfContents: true
  themeToggle: true
  copyright: Your organisation

  colors:
    dark: "#373b3e"
    neutral: "#bec8d1"
    accent: "#86cecb"
    support: "#137a7f"
    emphasis: "#e12885"

  homepage:
    latestTitle: From the lab
    latestCount: 3
    latestURL: /projects/

  footer:
    description: A longer description for the footer.
    license: Content is available under CC BY 4.0.

  social:
    - name: GitHub
      url: https://github.com/example
```

Place logo and favicon files in your site's `static/images` directory. The bundled Spudlab logo is the approved asset and must not be presented as another organisation's identity. Reusers should provide their own logo and colours.

Set `themeToggle: false` to remove the colour-theme control. The site will still respect the visitor's operating system preference.

### Homepage

Configure the homepage in `content/_index.md`:

```yaml
---
eyebrow: Open science, built in the open
heroTitle: Tools for better scientific data.
heroText: A clear sentence describing the work.
actions:
  - label: Explore projects
    url: /projects/
  - label: About us
    url: /about/
featuresEyebrow: Built with purpose
featuresTitle: What we do
featuresIntro: Optional text introducing the feature cards.
features:
  - number: 1
    title: Collect
    text: A short description.
    url: /projects/
---
```

The latest-content area draws from `params.mainSections`. It is omitted automatically when no matching pages exist. The feature area and hero note are also optional.

### Content front matter

Standard Hugo front matter works as expected. These optional values receive special treatment:

```yaml
---
title: Project title
date: 2026-10-24
lastmod: 2026-10-25
description: Used in cards and metadata.
status: Experimental
tags: [hardware, environment]
image: images/project-card.png
---
```

### Custom CSS and JavaScript

Files can be loaded after the theme assets without editing the theme. Paths are relative to your site's `static` directory.

```yaml
params:
  customCSS: [css/custom.css]
  customJS: [js/custom.js]
```

## Run the example

From the theme repository:

```sh
hugo server --source exampleSite --themesDir ../.. --theme spudlab-theme
```

Create a production build with:

```sh
hugo --source exampleSite --themesDir ../.. --theme spudlab-theme --minify
```

The repository includes `.github/workflows/pages.yml`, which builds and deploys the example site whenever `main` is updated. Before its first run, select **GitHub Actions** as the source under **Settings → Pages**. The workflow derives the correct Pages URL automatically, including the repository subpath.

## Accessibility

The theme is designed for WCAG-aware use, but site owners remain responsible for accessible content, meaningful alternative text, heading order, link wording, and verifying custom colour combinations. Do not rely on colour alone to communicate status or meaning.

## Licence

Licensed under the [Apache License 2.0](LICENSE). The included Spudlab logo remains Spudlab branding; its inclusion does not imply sponsorship, partnership, or endorsement.
