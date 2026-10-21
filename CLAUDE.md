# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site blog deployed to GitHub Pages at https://duanzy47.github.io. The site is titled "Maison Hatoyama" and uses the PaperMod theme with custom modifications.

## Development Commands

### Local Development
- `hugo server` - Start Hugo development server with live reload
- `hugo server -D` - Include draft posts in development server
- `hugo` - Build the static site to `./public` directory
- `hugo --minify` - Build with minification for production

### Theme Management
- `git submodule update --init --recursive` - Initialize/update theme submodules
- `git submodule update --remote` - Update themes to latest versions

## Site Architecture

### Directory Structure
- `content/posts/` - Blog post markdown files
- `content/archives.md`, `content/search.md` - PaperMod archive and search pages
- `static/img/` - Images and embedded HTML (e.g. plotly charts)
- `assets/css/extended/blog.css` - Small style overrides (CJK typography, home spacing, `.iframe-container`)
- `layouts/partials/comments.html` - Disqus comments (shortname "julian-10")
- `themes/` - Git submodules for themes (PaperMod is active, ananke is available)
- `config.toml` - Hugo configuration file

### Theme
The site is a plain minimalist blog on stock PaperMod. Avoid overriding PaperMod's
templates; put visual tweaks in `assets/css/extended/blog.css` and settings in `config.toml`.
The blog is for long-form essays (mostly Chinese) on ideas, the world, AI and society,
so prioritize readability.

## Deployment

The site automatically deploys via GitHub Actions (`.github/workflows/pages.yml`):
- Triggers on pushes to master branch
- Uses Hugo v0.115.4 extended (same as local)
- Builds with `--minify` and uploads to GitHub Pages
- Requires submodules to be checked out recursively

## Content Management

- Blog posts use front matter with `title`, `date`, and `draft` fields
- Images should be placed in `static/img/` and referenced with `/img/` paths
- Use `tags` in front matter to group posts (shown on /tags/)
- Use Hugo's figure shortcode for images with proper alt text