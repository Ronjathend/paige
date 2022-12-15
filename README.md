# Paige

A simple Hugo theme. [Try it out.](https://willfaught.com/paige)

## Screenshots

<img src="https://github.com/willfaught/paige/raw/master/images/screenshot.jpg">

Home page:

<img src="https://github.com/willfaught/paige/raw/master/images/home1.jpg">

<img src="https://github.com/willfaught/paige/raw/master/images/home2.jpg">

List page:

<img src="https://github.com/willfaught/paige/raw/master/images/list.jpg">

Single page:

<img src="https://github.com/willfaught/paige/raw/master/images/single.jpg">

Taxonomy page:

<img src="https://github.com/willfaught/paige/raw/master/images/taxonomy.jpg">

Term page:

<img src="https://github.com/willfaught/paige/raw/master/images/term.jpg">

404 page:

<img src="https://github.com/willfaught/paige/raw/master/images/404.jpg">

Search page:

<img src="https://github.com/willfaught/paige/raw/master/images/search.jpg">

## Features

- Accessibility
- Blog
- Bootstrap
- Customizable
- Facebook sharing
- Google Analytics
- Header links
- Landing page
- Light color scheme
- Math typesetting
- Menus
- Minimal design
- RSS with full content
- Responsive
- SEO
- Safari and Firefox Reader View support
- Search
- Sections
- Single column
- Social links
- Twitter sharing

Soon: Dark color scheme and dynamic color schemes, when Bootstrap 5.3 releases.

## Get started with Hugo

1. [Install Hugo](https://gohugo.io/installation/).

    For Homebrew on Mac:

    ```sh
    $ brew install hugo
    ```

2. Create a site:

    ```sh
    $ hugo new site yourproject
    ```

3. Create a post:

    ```sh
    $ cd yourproject
    $ hugo new my-post.md
    ```

See [Hugo's quick start guide](https://gohugo.io/getting-started/quick-start/) for more information.

## Install

### Option 1: Use a Hugo module

Example `config.yaml`:

```yaml
module:
  imports:
  - path: "github.com/willfaught/paige"
```

Install:

```sh
$ hugo mod init github.com/youraccount/yourproject
$ hugo mod get github.com/willfaught/paige
```

Update:

```sh
$ hugo mod get -u
```

### Option 2: Use a Git submodule

Example `config.yaml`:

```yaml
theme: "paige"
```

Install:

```sh
$ cd yourproject
$ git submodule add https://github.com/willfaught/paige themes/paige
$ git submodule update --init --recursive --remote
```

Update:

```sh
$ cd yourproject
$ git submodule update --recursive --remote
```

### Option 3: Use a copy

Example `config.yaml`:

```yaml
theme: "paige"
```

Install:

```sh
$ cd yourproject
$ git clone https://github.com/willfaught/paige themes/paige
$ rm -rf themes/paige/.git
```

Update:

```sh
$ cd yourproject
$ rm -rf themes/paige
$ git clone https://github.com/willfaught/paige themes/paige
$ rm -rf themes/paige/.git
```

## Run

```sh
$ hugo server -D
```

## Configure

Optional site parameters:

```yaml
math: true # Enable math typesetting with KaTeX
paigebootstrapstyles: "/my-assets/my-bootstrap.min.css" # Use local Bootstrap styles
paigebootstrapicons: "/my-assets/my-bootstrap-icons.css" # Use local Bootstrap icons
paigebootstrapscripts: "/my-assets/my-bootstrap.bundle.min.js" # Use local Bootstrap scripts
paigedateformat: "2006 January 2" # Hugo date format for page dates
paigehidethemecomment: true # Don't put a link to this project in a code comment
paigehidethemelink: true # Don't put a link to this project in the footer
```

If you set either `paigehidethemecomment` or `paigehidethemelink`, please credit this project in a post so others may find it.

Optional page parameters:

```yaml
link: "https://youtu.be/dQw4w9WgXcQ" # The reference for an anchor around the title
math: true # Enable math typesetting with KaTeX
paigeexcludesearch: true # Don't include this page in search results
```

Additional optional home page parameters:

```yaml
blurb: "There's a new daddy in town." # Displayed below the greeting
center: "my-center.jpg" # An image that is centered
greeting: "You know best" # Displayed below the center and stretch images
stretch: "my-stretch.jpg" # A 4x3 or panorama image that is stretched fully horizontally
```

Additional optional list page parameters:

```yaml
paigeshowfullpages: true # Show full pages, not just page titles and descriptions
```

Additional optional single page parameters:

```yaml
paigeexcluderss: true # Don't include this page in RSS feeds
```

Example `config.yaml`:

```yaml
author:
  email: example@example.com
  name: Michael Bluth
baseurl: https://example.com
copyright: © Michael Bluth
languagecode: en-us
enablerobotstxt: true
markup:
  goldmark:
    renderer:
      unsafe: true
  highlight:
    style: vs
menu:
  main:
  - identifier: home
    name: Home
    url: /
    weight: 10
  - identifier: about
    name: About
    url: /about/
    weight: 20
  - identifier: blog
    name: Blog
    url: /blog/
    weight: 30
  - identifier: categories
    name: Categories
    url: /categories/
    weight: 40
  - identifier: tags
    name: Tags
    url: /tags/
    weight: 50
  - identifier: search
    name: Search
    url: /search/
    weight: 60
outputs:
  home:
  - html
  - json
  - rss
paginate: 50
permalinks:
  blog: /blog/:year/:month/:day/:title/
social:
  envelope: mailto:example@example.com
  discord: https://discord.com/users/example
  github: https://github.com/example
  facebook: https://facebook.com/example
  instagram: https://instagram.com/example
  linkedin: https://www.linkedin.com/in/example
  reddit: https://reddit.com/u/example
  twitch: https://www.twitch.tv/example
  twitter: https://twitter.com/example
  youtube: https://www.youtube.com/user/example
theme: paige
timezone: America/Los_Angeles
title: No Borders, No Limits
titlecasestyle: Go
```

## Search

The `paige-search` layout provides full site search.

Example `config.yaml`:

```yaml
outputs:
  home: ["html", "json", "rss"]
```

Example `content/search.md`:

```yaml
---
layout: paige-search
title: Search
---
```

## Customization

If `partials/paige-head-last.html` exists in the site, it is included at the end of the head tag.
If `partials/paige-body-last.html` exists in the site, it is included at the end of the body tag.

Most code is in partial templates that are included by the default layouts.
Elements can easily be added or changed by overriding the corresponding layout or partial template.

For example, the default layouts `home.html`, `list.html`, `single.html`, `taxonomy.html`, and `term.html` include `paige-main.html`, which includes `paige-title.html`, `paige-description.html`, `paige-date.html`, and `paige-content.html`. To change the page title for all those layouts, change `paige-title.html`. To change the page title for `single.html`, replace the use of `paige-main.html` in `single.html` with the use of `paige-title.html`, `paige-description.html`, `paige-date.html`, and `paige-content.html`, then replace that use of `paige-title.html` with your own design.

## Design

The HTML author is the site author.

The HTML description is the page description.

The HTML keywords is a union of the page keywords, tags, and categories.

The HTML title is the page title, followed by a middle dot, followed by the site title.
If one is missing, the other is used without the middle dot.
For the home page, the title is the page title, if any, or the site title otherwise.

The HTML body can have a header, a body, and a footer.
The header has the menu, if any; the page title, if any; the page description, if any; and the page date, if any.
The body has the page content, if any.
The footer has the copyright notice, if any, and the theme link, if any.

The page title and description can be Markdown. Markup is stripped for HTML titles.

The page date is the publish date, if any; otherwise, it's the creation date.

Bootstrap 5.2.2 CSS and JavaScript and Bootstrap Icons 1.10.2 are loaded from the Bootstrap CDN for every page unless local Bootstrap assets are used instead.

## Credits

- Center photo by [Yuvraj Singh](https://unsplash.com/photos/ljziSm0DXg8)
- Stretch photo by [Sergey Pesterev](https://unsplash.com/photos/JV78PVf3gGI)

## Community

Get started by [starring](https://github.com/willfaught/paige/stargazers)
and [following](https://github.com/willfaught/paige/watchers) the project.

If you find an issue, please [report it](https://github.com/willfaught/paige/issues/new).
If you have fixes or improvements, please [create a pull request](https://github.com/willfaught/paige/compare).
Feedback is encouraged and appreciated.

## Project

Created by [Will Faught](https://github.com/willfaught).
Released under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
Hosted at https://github.com/willfaught/paige.
