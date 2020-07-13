# Just Build the Docs

<!-- @TODO: Banner  -->

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-green.svg)](https://github.com/RichardLitt/standard-readme)

_Features that extend the excellent "Just the docs" Jekyll theme_

<!-- @TODO: Add Table of Contents when README becomes longer than 100 lines -->

Currently this project has implemented two features:

1. Exclude from `_config.yml_
2. Recursive menu
3. Cross-repository menu

These features have been built for and are used with Github Pages.

Other Jekyll use-cases have not been tested and may contain bugs or not work at
all.

## Install

The recommended way to install this project is by installing it as a remote
theme. In your project's `_config.yml` add:

```yml
remote_theme: Potherca/just-build-the-docs@theme
```

## Usage

After it has been installed and configured, the theme should "just work".

To use a feature, it must be enabled in the `_config.yml` file under the `nav`
section.

### Exclude from `_config.yml_

```yml
nav:
  exclude:
    # The URL of any page that should not be displayed in the navigation menu
    - "/"
```
### Recursive menu

```yml
nav:
  recurse: true
```

### Cross-repository menu

```yml
nav:
  cross_repository:
    # Set to true to also include repositories that have been archived
    show_archived: false
    #set to true to use the homepage (from the repository settings) instead of https://site.url/repository-name
    show_homepage: false
```

## Example of all features combined

```yml
nav:
  exclude:
    - "/"
  recurse: true
  cross_repository:
    show_archived: false
    show_homepage: true
```

## Contributing

Questions or feedback can be given by [opening an issue](https://github.com/Potherca/renovate-config/issues).

<!--
@TODO: Link to a CONTRIBUTING file
@TODO: Link to a Code of Conduct
-->

## License

This project has been published by [Potherca](https://pother.ca) under a [Mozilla Public License 2.0 (MPL-2.0)](./LICENSE).
