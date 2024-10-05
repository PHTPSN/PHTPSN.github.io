---
author: "PHTPSN"
title: "Start Now!"
date: "2024-9-25 (A date I was once scared...)"
description: "Sample article showcasing basic Markdown syntax and formatting for HTML elements."
tags: ["markdown", "css", "html", "themes"]
categories: ["themes", "syntax"]
series: ["Themes Guide"]
aliases: ["migrate-from-jekyl"]
cover:
  image: images/msg.png
  caption: "Generated using [OG Image Playground by Vercel](https://og-playground.vercel.app/)"
ShowToc: true
TocOpen: true
---

## Installation

Reference: https://gohugo.io/installation/

- Git
- Go

## Configure the Site

Use Git cmd

1. Input commands:

    ``` bash
    cd D:\HugoSites
    hugo new site MyNewSite
    git init
    ```

2. Download your favorite theme on hugo website.
3. Duplicate theme data into "theme" folder in your local repository.
4. Duplicate "Content" and "hugo.yaml" in exampleSite into the main folder of your local repository. Delete "hugo.toml" and "content/post/rich-content".
5. Change the value of "theme" in "config.yaml" to the name of the theme folder.
   eg:

   ```yaml
   baseURL: "https://adityatelange.github.io/hugo-PaperMod/"
   title: PHTPSN's WebSite
   copyright: "© [PaperMod Contributors](https://github.com/adityatelange/hugo-PaperMod/graphs/contributors)"
   paginate: 5
   theme: [hugo-PaperMod-master]
   ```

Use `hugo server` to generate url to preview.

## Publish the Site

In github:

1. Create a new repository XXXX.github.io.
2. Change Settings - Pages - Build and deployment - Source to "Github Actions".
3. Add a new file `.github/workdflow/hugo.yml` with content as follow, and change `jobs: bulid: env: HUGO_VERSION` to your hugo version. Use `hugo version` to see.

```yaml
# Sample workflow for building and deploying a Hugo site to GitHub Pages
name: Deploy Hugo site to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["main"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

# Default to bash
defaults:
  run:
    shell: bash

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.134.3
    steps:
      - name: Install Hugo CLI
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
          && sudo dpkg -i ${{ runner.temp }}/hugo.deb
      - name: Install Dart Sass
        run: sudo snap install dart-sass
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5
      - name: Install Node.js dependencies
        run: "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
      - name: Build with Hugo
        env:
          HUGO_CACHEDIR: ${{ runner.temp }}/hugo_cache
          HUGO_ENVIRONMENT: production
        run: |
          hugo \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

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
        uses: actions/deploy-pages@v4
```


```bash
git remote add origin https://github.com/XXXX/XXXX.github.io.git
git add .
git commit -m "Add workflow"
git push origin main
```

Or

```bash
hugo
```

ps. If cmd reminds "Please tell me who you are", input:

```bash
git config user.email "XXXX@XXXX"
git config user.name "XXXX"
```

ps. If your current local brach is behind its remote counterpart, use `git pull origin main --allow-unrelated-histories` to sync.

In github:

See in Action if a new workflow has run successfully.
