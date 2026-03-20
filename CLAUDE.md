# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Testival is a content repository archiving presentations and materials from the Testival software testing community meetups and conferences (https://testival.eu/, https://www.meetup.com/testival/).

This is **not a software project** — there are no build, test, or lint commands.

## Repository Structure

- `files/` — Numbered subdirectories (e.g., `files/73/`) each corresponding to a Testival meetup event. Contains PDF slides, PPTX files, and occasionally videos or other materials.
- `at-meetup.md` — Checklist/script for running a meetup.
- `at-conference.md` — Checklist/script for running a conference.

## Development Environment

This repository uses a **devcontainer** (`.devcontainer/devcontainer.json`) with a Jekyll image. The host machine does not have Ruby installed. All commands (Ruby, Bundler, Jekyll, gem, etc.) must be run inside the devcontainer using `docker exec`.

## Conventions

- **Commits:** The user makes all commits. Never offer to commit.
- **Commit messages** follow the pattern: `meetup: slides from #<number>` (e.g., `meetup: slides from #73`).
- **Branch:** All work is on `master`.
- New event materials go into `files/<event-number>/`.
