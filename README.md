# Privacy Hermit - a theme for Hugo

Privacy Hermit is a fork of the original [Hermit](https://github.com/Track3/hermit) theme from [Track3](https://github.com/Track3)
with privacy in mind. It is a minimal and fast theme for Hugo, built for bloggers who want a simple and focused website.

![Overview](https://github.com/nodeg/prv-hermit/raw/main/images/screenshot.png)

## Features

* A single-column layout and carefully crafted typography offers a great reading experience.
* Navigations and functions are placed in the bottom bar which will hide when you scroll down.
* Featured image is supported. It will be displayed as a dimmed background of the page.
* Displays all of your posts on a single page, with one section per year, simple and compact.
* Extremely lightweight and load fast. No third party framework, no unnecessary code.
* All code fields feature syntax highlighting and a code-copy function
* Responsive & Retina Ready. Scales gracefully from a big screen all the way down to the smallest mobile phone. Assets
  in vector format ensures that it looks sharp on high-resolution screens.

![Comparison](https://github.com/nodeg/prv-hermit/raw/main/images/hermit.png)

## Getting started

### Installation

Run this command from the root of your Hugo directory:

```bash
git clone https://github.com/nodeg/prv-hermit.git themes/hermit
```

Or, if your Hugo site is already in git, you can include this repository as a [git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules).
This makes it easier to update this theme. For this you need to run:

```bash
git submodule add https://github.com/nodeg/prv-hermit.git themes/hermit
```

Alternatively, if you are not familiar with git, you can download the theme as a `.zip` file, unzip the theme contents
and then move the unzipped source into your `themes` directory.

For more information, read the official [documentation](https://gohugo.io/themes/installing-and-using-themes/) of Hugo.

### Configuration

The example config file can be found in the theme's `exampleSite` folder. You can just copy the `config.toml` to the
root directory of your Hugo site. There are instructions in the example config file, feel free to change strings as you
like to customize your website.

#### Favicon

Use [RealFaviconGenerator](https://realfavicongenerator.net/) to generate these files, put them into your site's
`static` folder:

* android-chrome-192x192.png
* android-chrome-512x512.png
* apple-touch-icon.png
* favicon-16x16.png
* favicon-32x32.png
* favicon.ico
* mstile-150x150.png
* safari-pinned-tab.svg
* site.webmanifest

#### Social icons

The following icons are supported, please make sure the `name` filed is exactly one of these:

| name            |             |              |           |
| --------------- | ----------- | ------------ | --------- |
| `email`         | `codepen`   | `facebook`   | `github`  |
| `gitlab`        | `instagram` | `linkedin`   | `slack`   |
| `stackoverflow` | `telegram`  | `twitter`    | `youtube` |
| `shutterstock`  | `freepik`   | `adobestock` | `123rf`   |

| `twitch`        | `qq`        |              |           |

If that's not enough, you can see [Overriding templates](#overriding-templates) section.

### Manage content

* Keep your regular pages in the `content` folder. To create a new page, run `hugo new page-title.md`
* Keep your blog posts in the `content/posts` folder. To create a new post, run `hugo new posts/post-title.md`

### More customizations

#### Overriding templates

In Hugo, layouts can live in either the project’s (root) or the themes’ layout folders, any template inside the root
layout folder will override theme's layout that relative to it, for example: `layouts/_default/baseof.html` will
override `themes/hermit/layouts/_default/baseof.html`. So, you can easily customize the theme without edit it directly,
which makes updating the theme easier. Here's some common customizations:

##### Customize social icons

You can modify or add any svg icons in site's `layouts/partials/svg.html`.

##### Customize comment system

We only have built-in support for Disqus at the moment, if that doesn't fit your needs, you can just add html to site's
`layouts/partials/comments.html`.

#### Customize CSS

If you'd like to customize theme color or fonts, you can simply override `assets/scss/_predefined.scss`, by simply copy
it to site's root (keep the same relative path) then edit those variables. But keep in mind, you'll need
**Hugo extended version** which has the ability to rebuild SCSS. You don't have to use extended version in production
but in this case it's necessary to make sure the `resources` folder is committed and "up to date" (by running `hugo` or
`hugo server` locally using the extended version). But anyway, always use the extended version if you can.

For adding other custom CSS to the theme, you can assign an array of references in `config.toml` like following:

```toml
[params]
  customCSS = ["css/foo.css", "css/bar.css"]
```

You may reference as many stylesheets as you want. Their paths need to be relative to the `static` folder or it can be
a full URL for external resources.

#### Code injection

You can inject any html code to every page's document head or right above the closing body tag. This makes it easier to
add any html meta data, custom css/js, dns-prefetch etc. To do this you simply need to create a file at site's
`layouts/partials/extra-head.html` or `layouts/partials/extra-foot.html`, code inside will be injected to every page.

## Acknowledgments

* The original [Hermit theme](https://github.com/Track3/hermit) from Track3 - [MIT](https://github.com/Track3/hermit/blob/master/LICENSE)
* [normalize.css](https://necolas.github.io/normalize.css/) - [MIT](https://github.com/necolas/normalize.css/blob/master/LICENSE.md)
* [animate.css](https://daneden.github.io/animate.css/) - [MIT](https://github.com/daneden/animate.css/blob/master/LICENSE)
* [feather](https://feathericons.com/) - [MIT](https://github.com/feathericons/feather/blob/master/LICENSE)
* [code-copy.js](assets/js/code-copy.js) - [Tom Spencer](https://www.fiznool.com/blog/2018/09/14/adding-click-to-copy-buttons-to-a-hugo-powered-blog/)
