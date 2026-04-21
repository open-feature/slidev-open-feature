# OpenFeature Slidev Theme

[![NPM version](https://img.shields.io/npm/v/@openfeature/slidev-theme-open-feature?color=3AB9D4&label=)](https://www.npmjs.com/package/@openfeature/slidev-theme-open-feature)

An [OpenFeature](https://openfeature.dev)-branded theme for [Slidev](https://github.com/slidevjs/slidev). It features the official OpenFeature color palette, wave-style background decorations, and Poppins / Architects Daughter typography — with full support for light and dark mode.

## Install

Add the following frontmatter to your `slides.md`. Start Slidev then it will prompt you to install the theme automatically.

```md
---
theme: '@openfeature/slidev-theme-open-feature'
---
```

Learn more about [how to use a theme](https://sli.dev/guide/theme-addon#use-theme).

## Layouts

This theme provides the following layouts:

| Layout | Description |
|--------|-------------|
| `cover` | Title slide with centered content and prominent wave background |
| `default` | Standard content slide with a title bar and body area |
| `end` | Closing slide with centered content and prominent wave background |
| `image-left` | Two-column layout with an image on the left (e.g., `image: path/to/image.jpg`) |
| `image-right` | Two-column layout with an image on the right (e.g., `image: path/to/image.jpg`) |
| `intro` | Introduction / about slide with centered content |
| `section` | Section divider with large centered heading |
| `two-cols` | Two-column layout using default and `::right::` slots |

## Components

This theme provides the following components:

### `<OpenFeatureLogo>`

Renders the official OpenFeature horizontal wordmark logo with automatic light/dark mode support.

| Prop   | Type     | Default   | Description        |
|--------|----------|-----------|--------------------|
| `size` | `string` | `'200px'` | Width of the logo. |

```md
<OpenFeatureLogo size="250px" />
```

### `<PresenterProfile>`

Displays a presenter's photo (or initials fallback), name, and company.

| Prop      | Type     | Default  | Description                                          |
|-----------|----------|----------|------------------------------------------------------|
| `name`    | `string` | —        | **Required.** Presenter's full name.                 |
| `company` | `string` | —        | Company or organization name.                        |
| `photo`   | `string` | —        | URL or path to the presenter's photo.                |
| `size`    | `string` | `'80px'` | Diameter of the avatar circle.                       |

When `photo` is omitted, the avatar displays the presenter's initials on an accent-colored background.

The `photo` prop accepts both remote URLs and local files placed in the `public/` directory:

```md
<!-- Remote URL -->
<PresenterProfile name="Jane Doe" company="CNCF" photo="https://example.com/jane.jpg" />

<!-- Local file from public/ -->
<PresenterProfile name="Jane Doe" company="CNCF" photo="/images/jane.jpg" />
```

### `<QRCode>`

Generates and displays a QR code from a URL. Rendered client-side with no network dependency.

| Prop      | Type     | Default         | Description                          |
|-----------|----------|-----------------|--------------------------------------|
| `url`     | `string` | —               | **Required.** The URL to encode.     |
| `size`    | `string` | `'200px'`       | Width and height of the QR code.     |
| `color`   | `string` | `'#000000'`     | Foreground color of the QR code.     |
| `bgColor` | `string` | `'#ffffff'`     | Background color of the QR code.     |

```md
<QRCode url="https://openfeature.dev" size="200px" />
```

## Contributing

- `npm install`
- `npm run dev` to start theme preview of `example.md`
- Edit the `example.md` and style to see the changes
- `npm run export` to generate the preview PDF
- `npm run screenshot` to generate the preview PNG

> **Note:** Node.js >= 18 is required. The repo includes an `.nvmrc` (Node 22) — run `nvm use` to pick it up.
