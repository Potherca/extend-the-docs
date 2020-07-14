# Extend the Docs

<!-- @TODO: Banner  -->

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-green.svg)](https://github.com/RichardLitt/standard-readme)

_Features that extend the excellent "Just the docs" Jekyll theme_

<!-- toc -->

- [Install](#install)
- [Usage](#usage)
  - [Cross-repository menu](#cross-repository-menu)
  - [Exclude from `_config.yml`](#exclude-from-_configyml)
  - [Include posts in the menu](#include-posts-in-the-menu)
  - [Recursive menu](#recursive-menu)
- [Example of all features combined](#example-of-all-features-combined)
- [Contributing](#contributing)
- [License](#license)

<!-- tocstop -->

Currently this project has implemented these features:

1. Cross-repository menu
2. Exclude from `_config.yml`
3. Include posts in the menu
4. Recursive menu

These features have been built for and are used with Github Pages.

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
organisation) `nav.cross_repository` can be set in the `_config.yml` using:


```yml
nav:
  cross_repository:
    # Set to true to also include repositories that have been archived
    show_archived: false
    #set to true to use the homepage (from the repository settings) instead of https://site.url/repository-name
    show_homepage: false
```

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

### Recursive menu

The navigation menu can follow the structure of documents in a repository for
the parent/child structure, instead of using the frontmatter.

To do this, set `nav.recurse` to `true`:

```yml
nav:
  recurse: true
```

## Example of all features combined

```yml
nav:
  cross_repository:
    show_archived: false
    show_homepage: true
  exclude:
    - "/404.html"
  include_posts:
    sort_by_date: true
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
