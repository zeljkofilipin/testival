# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Testival is a Jekyll website hosted on GitHub Pages at [testival.eu](https://testival.eu/), archiving presentations and blog posts from the Testival software testing community meetups and conferences (https://www.meetup.com/testival/).

There are no build, test, or lint commands to run locally. The site builds automatically on GitHub Pages.

## Repository Structure

- `_posts/` — 134 Jekyll blog posts (Markdown with YAML front matter). Named `YYYY-MM-DD-title.md`.
- `_layouts/default.html` — Custom HTML layout (replaces the minima theme default).
- `_config.yml` — Jekyll configuration. Theme: `minima`. Permalink: `/:year/:month/:day/:title/`.
- `index.md` — Homepage listing all posts.
- `tags.md` — Tags page at `/tags/`, groups posts by tag (sorted descending).
- `files/` — Numbered subdirectories (e.g., `files/73/`) each corresponding to a Testival meetup event. Contains PDF slides, PPTX files, and occasionally videos or other materials. Excluded from the Jekyll build.
- `at-meetup.md` — Checklist/script for running a meetup. Excluded from the Jekyll build.
- `at-conference.md` — Checklist/script for running a conference. Excluded from the Jekyll build.
- `CNAME` — Custom domain (`testival.eu`).
- `Gemfile` — Single dependency: `github-pages`.

## Post Format

Posts use this front matter structure:

```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS
author: authorname
tags:
  - 2025
  - conference
  - english
  - testival
---
```

Tags are sorted alphabetically. Common tags: year (`2025`), language (`english`, `hrvatski`), event type (`conference`, `meetup`), era (`testival`, `viaqa`, `software testing club`).

## Development Environment

This repository uses a **devcontainer** (`.devcontainer/devcontainer.json`) with a Jekyll image (`mcr.microsoft.com/devcontainers/jekyll:2-bullseye`). The host machine does not have Ruby installed. All commands (Ruby, Bundler, Jekyll, gem, etc.) must be run inside the devcontainer using `docker exec`. The dev server runs on port 4000 and automatically rebuilds when files change — no need to restart it.

## Conventions

- **Commits:** The user makes all commits. Never offer to commit.
- **Commit messages** use a `topic: description` format (e.g., `meetup: slides from #73`, `tags: display descending`).
- **Branch:** All work is on `master`.
- New event materials go into `files/<event-number>/`.
