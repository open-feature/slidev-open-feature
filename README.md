# OpenFeature Slidev Theme

[![NPM version](https://img.shields.io/npm/v/@openfeature/slidev-theme-open-feature?color=3AB9D4&label=)](https://www.npmjs.com/package/@openfeature/slidev-theme-open-feature)

An [OpenFeature](https://openfeature.dev)-branded theme for [Slidev](https://github.com/slidevjs/slidev). It features the official OpenFeature color palette, wave-style background decorations, and Poppins / Architects Daughter typography — with full support for light and dark mode.

## Install

Add the following frontmatter to your `slides.md`. Start Slidev then it will prompt you to install the theme automatically.

<pre><code>---
theme: <b>@openfeature/slidev-theme-open-feature</b>
---</code></pre>

Learn more about [how to use a theme](https://sli.dev/guide/theme-addon#use-theme).

## Layouts

This theme provides the following layouts:

| Layout | Description |
|--------|-------------|
| `cover` | Title slide with centered content and prominent wave background |
| `default` | Standard content slide with a title bar and body area |
| `end` | Closing slide with centered content and prominent wave background |
| `image-left` | Two-column layout with an image on the left (`image` prop required) |
| `image-right` | Two-column layout with an image on the right (`image` prop required) |
| `intro` | Introduction / about slide with centered content |
| `section` | Section divider with large centered heading |
| `two-cols` | Two-column layout using default and `::right::` slots |

## Components

This theme provides the following components:

> TODO:

## Contributing

- `npm install`
- `npm run dev` to start theme preview of `example.md`
- Edit the `example.md` and style to see the changes
- `npm run export` to generate the preview PDF
- `npm run screenshot` to generate the preview PNG

> **Note:** Node.js >= 18 is required. The repo includes an `.nvmrc` (Node 22) — run `nvm use` to pick it up.
