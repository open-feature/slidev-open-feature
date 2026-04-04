# slidev-theme-open-feature

[![NPM version](https://img.shields.io/npm/v/slidev-theme-open-feature?color=3AB9D4&label=)](https://www.npmjs.com/package/slidev-theme-open-feature)

A (...) theme for [Slidev](https://github.com/slidevjs/slidev).

<!--
  Learn more about how to write a theme:
  https://sli.dev/guide/write-theme.html
--->

<!--
  run `npm run dev` to check out the slides for more details of how to start writing a theme
-->

<!--
  Put some screenshots here to demonstrate your theme

  Live demo: [...]
-->

## Install

Add the following frontmatter to your `slides.md`. Start Slidev then it will prompt you to install the theme automatically.

<pre><code>---
theme: <b>open-feature</b>
---</code></pre>

Learn more about [how to use a theme](https://sli.dev/guide/theme-addon#use-theme).

## Layouts

This theme provides the following layouts:

> TODO:

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
