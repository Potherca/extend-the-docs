# Extend the Docs

<!-- @TODO: Banner  -->

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-green.svg)](https://github.com/RichardLitt/standard-readme)

_Features that extend the excellent "Just the docs" Jekyll theme_

<!-- toc -->

- [Install](#install)
- [Usage](#usage)
  - [Cross-repository menu](#cross-repository-menu)
    - [Always use links from homepage setting](#always-use-links-from-homepage-setting)
    - [Excluding repositories](#excluding-repositories)
    - [Hiding archived repositories](#hiding-archived-repositories)
    - [Example of all cross-repostory settings](#example-of-all-cross-repostory-settings)
  - [Custom favicon path](#custom-favicon-path)
  - [Exclude from `_config.yml`](#exclude-from-_configyml)
  - [Include posts in the menu](#include-posts-in-the-menu)
  - [Main title customization](#main-title-customization)
  - [Recursive menu](#recursive-menu)
- [Example of all settings](#example-of-all-settings)
- [Contributing](#contributing)
- [License](#license)

<!-- tocstop -->

Currently this project has implemented these features:

1. Cross-repository menu
2. Custom favicon path
3. Exclude from `_config.yml`
4. Include posts in the menu
5. Main title customization
6. Recursive menu

These features have been built for and are used with GitHub Pages.

Other Jekyll use-cases have not been tested and may contain bugs or not work at
all.

## Install

The recommended way to install this project is by installing it as a remote
theme. In your project's `_config.yml` add:

```yml
remote_theme: Potherca/extend-the-docs@theme
```

## Usage

After it has been installed and configured, the theme should "just work".

To use a feature, it must be enabled in the `_config.yml` file under the `nav`
section.

### Cross-repository menu

To have the top-level of the navigation menu be all repositories of a user (or
organisation) the `nav.cross_repository` value can be set in the `_config.yml`:

```yml
nav:
  cross_repository: true
```

All links point to the GitHub Pages URL of each repository or, if no GitHub
Pages are available, to the homepage set for the repository. If neither is
available, no link is shown.

#### Always use links from homepage setting

To always use the repository homepage, set `nav.cross_repository.show_homepage`
to `true`.

```yml
nav:
  cross_repository:
    show_homepage: true
```

#### Excluding repositories

Any repositories that should be excluded can be set in `nav.cross_repository.exclude`.

```yml
nav:
  cross_repository:
    exclude:
      - example.github.io
```

#### Hiding archived repositories

By default, archived repositories are also shown in the navigation menu. They
can be hidden by setting `nav.cross_repository.show_archived` to `false`.

```yml
nav:
  cross_repository:
    show_archived: false
```

#### Example of all cross-repostory settings

```yml
nav:
  cross_repository:
    # Any repository mentioned here will not be included in the navigation menu
    exclude:
      - potherca.github.io
    # Set to true to also include repositories that have been archived
    show_archived: false
    # Set to true to use the homepage (from the repository settings) instead of https://site.url/repository-name
    show_homepage: true
```

### Custom favicon path

A custom path to the favicon can be set in the `_config.yml` using:

```yml
nav:
  favicon_ico: /favicon.ico
```

Please note that this path is used as-is (i.e. it is _not_ a relative path
within the repo).

### Exclude from `_config.yml`

To exclude pages, they can be added to `nav.exclude`, instead of adding
frontmatter:

```yml
nav:
  exclude:
    # The URL of any page that should not be displayed in the navigation menu
    - "/404.html"
```

### Include posts in the menu

<kbd>
<strong>⚠️ This feature only works if `nav.recurse` is enabled.</strong>
</kbd>

By default, pages are not added to the menu structure. To include posts, set
`nav.include_posts` to `true`:

```yml
nav:
    include_posts: true
```

By default, posts will be sorted by their title, not by publishing date.

To sort by date instead of title:

```yml
nav:
  include_posts:
    sort_by_date: true
```

### Main title customization

The link or text displayed for the main link can be changed:

```
nav:
  main_title:
    link: '/'
    text: Alternative Title
```

This can be useful to link to a generic homepage rather than repository home.

### Recursive menu

The navigation menu can follow the structure of documents in a repository for
the parent/child structure, instead of using the frontmatter.

To do this, set `nav.recurse` to `true`:

```yml
nav:
  recurse: true
```

## Example of all settings

```yml
nav:
  cross_repository:
    exclude:
      - example.github.io
    show_archived: false
    show_homepage: true
  exclude:
    - "/404.html"
  favicon_ico: /favicon.ico
  include_posts:
    sort_by_date: true
  main_title:
    link: '/'
    text: Alternative Title
  recurse: true
```

## Contributing

Questions or feedback can be given by [opening an issue on GitHub](https://github.com/Potherca/extend-the-docs/issues).

Like all Potherca's projects, [this project adheres to the Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md)

<!--
@TODO: Link to a CONTRIBUTING file
-->

## License

This project has been published by [Potherca](https://pother.ca) under a [Mozilla Public License 2.0 (MPL-2.0)](./LICENSE).
