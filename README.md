# Hugo Theme Olive

Jizo Games Original Hugo Theme

[![Minimum Hugo Version](https://img.shields.io/static/v1?label=min-HUGO-version&message=0.146.0&color=blue&logo=hugo)](https://github.com/gohugoio/hugo/releases/tag/0.146.0)
[![GitHub](https://img.shields.io/github/license/jizogames/hugo-olive)](https://github.com/jizogames/hugo-olive/blob/main/LICENSE)

## Site Configuration

### Header

| Name | Default | Description |
|---|:---:|---|
| `params.header.logo` | `""` | Path to the header logo image. |
| `params.header.disableTextInHeader` | `false` | Hide the site title in the header. |
| `params.header.maxLogoSize` | '80.0' | Maximum display size of the logo. |

### Footer

| Name | Default | Description |
|---|:---:|---|
| `params.footer.showMenu` | `true` | Show the footer menu. |

### Breadcrumb

| Name | Default | Description |
|---|:---:|---|
| `params.breadcrumb.showBreadcrumb` | `true` | Show breadcrumbs. |
| `params.breadcrumb.showCurrentPage` | `true` | Show the current page in breadcrumbs. |

## Documentation

### Header

The header outputs the site logo and the main menu.

The site logo can be composed of a logo image and the site title.

By default, the site title is displayed with the logo image.

Set the logo image path in your site configuration.

```toml
[params.header]
logo = "images/logo.png"
maxLogoSize = 80.0
```

If `params.header.logo` is set, the logo image will be displayed.

The logo image is displayed at half of its original pixel size.
For example, if you want to display the logo at `80px`, prepare a `160px` image.

`maxLogoSize` sets the maximum display size of the logo.
If either the width or height exceeds this value, the logo will be scaled down while preserving its aspect ratio.

If you want to use only the logo image without the site title, set `disableTextInHeader` to `true`.

```toml
[params.header]
disableTextInHeader = true
```

When the site title is displayed, the logo image is treated as decorative and uses an empty `alt` attribute.
When the site title is hidden, the logo image becomes the home link and uses the site title as its alternative text.

---

### Footer

The footer outputs a copyright notice and can also display a footer menu.

The footer menu is displayed when `showMenu` is set to `true`.

The footer menu is generated from the `footer` menu configuration.

```toml
[[menus.footer]]
name = "About"
pageRef = "/about"
weight = 10
```

If you do not want to display the footer menu, set `showMenu` to `false`.

```toml
[params.footer]
showMenu = false
```

The copyright year is generated automatically.

---

### Breadcrumb

Breadcrumbs are displayed by default.

The breadcrumb trail is generated in the following order:
```text
Home > Ancestor sections > Category > Current page
```

The first category assigned to the page is used in the breadcrumb.

You can configure breadcrumbs globally.

```toml
[params.breadcrumb]
showBreadcrumb = true
showCurrentPage = true
```

You can also override the breadcrumb settings per page.

```toml
+++
title = "Example Page"

[params.breadcrumb]
showBreadcrumb = false
+++
```

To hide only the current page from the breadcrumb, use:
```toml
+++
title = "Example Page"

[params.breadcrumb]
showCurrentPage = false
+++
```

---

### Taxonomies

This theme uses Hugo's default taxonomies:
```toml
[taxonomies]
category = "categories"
tag = "tags"
```

If you add custom taxonomies, make sure to keep `categories` and `tags` if you want to continue using the theme's category and tag features.

For example:
```toml
[taxonomies]
category = "categories"
tag = "tags"
series = "series"
```

