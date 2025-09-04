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
- `static/` - Static assets (images in `static/img/`, custom CSS in `static/css/`)
- `layouts/` - Custom Hugo template overrides (currently has custom single.html with Disqus integration)
- `themes/` - Git submodules for themes (PaperMod is active, ananke is available)
- `config.toml` - Hugo configuration file

### Theme Configuration
The site uses Hugo PaperMod theme with:
- Custom single post template at `layouts/_default/single.html` that includes Disqus comments
- Custom CSS at `static/css/custom.css` for iframe responsive containers
- Disqus integration configured with shortname "julian-10"

### Content Structure
- Posts are in Chinese and English
- Images referenced with Hugo figure shortcodes: `{{< figure src="/img/filename.ext" alt="description" >}}`
- Custom CSS class `.iframe-container` for responsive embedded content

## Deployment

The site automatically deploys via GitHub Actions (`.github/workflows/pages.yml`):
- Triggers on pushes to master branch
- Uses Hugo v0.99.0 extended
- Builds with `--minify` and uploads to GitHub Pages
- Requires submodules to be checked out recursively

## Windows 98 Retro Theme

This blog has been completely customized with a Windows 98 retro aesthetic:

### Theme Features
- **Desktop Environment**: Full Windows 98 desktop with taskbar, running clock, and window controls
- **Window UI**: All content is presented in Windows 98 style windows with title bars, menu bars, and status bars
- **File Explorer**: Blog posts are displayed in a file explorer interface with icons and metadata
- **Navigation**: Side navigation window that appears on non-single pages
- **Interactive Elements**: Buttons, form controls, and UI elements all styled as Windows 98 components
- **Typography**: MS Sans Serif font family for authentic Windows 98 look
- **Color Scheme**: Classic Windows 98 gray (#c0c0c0) with proper beveled borders and shadows

### Custom Templates
- `layouts/_default/baseof.html` - Main template with desktop environment and taskbar
- `layouts/_default/single.html` - Individual blog post in window format with title bar and menu
- `layouts/_default/list.html` - File explorer style listing for homepage and archives
- `static/css/custom.css` - Complete Windows 98 CSS framework with:
  - Window styling (raised/sunken borders)
  - Button and form controls
  - Taskbar and desktop background
  - File explorer components
  - Responsive adjustments

### Theme Customizations

When modifying the theme:
- All styling is in `static/css/custom.css` - edit this file for visual changes
- Templates use Windows 98 UI classes: `.window`, `.title-bar`, `.btn`, `.fieldset`, etc.
- The theme completely overrides PaperMod styling
- Desktop background uses teal color with subtle pattern
- Interactive JavaScript for clock and button press effects

## Content Management

- Blog posts use front matter with `title`, `date`, and `draft` fields
- Images should be placed in `static/img/` and referenced with `/img/` paths
- Use Hugo's figure shortcode for images with proper alt text