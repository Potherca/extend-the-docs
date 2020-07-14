# Development notes and general ideas

## Changes to original files

Instead of overwriting files in `_layouts` and `_includes` it might be neater to
use something simliar to `_layouts/table_wrappers.html` to replace specific HTML
with the replacement:

```
---
layout: vendor/compress
---

{% assign content_ = content | replace: '<table', '<div class="table-wrapper"><table' %}
{% assign content_ = content_ | replace: '</table>', '</table></div>' %}
{{ content_ }}
```
There's more possible with this than one would think at first. Care needs to be
taken when/where things are replaced as there is the risk of a performance
penalty running logic in the originals for nothing.

The major benefit being:

- Leaving the commit history of the original intact
- Easier to integrate upstream changes

## Cross-repository

It might be a good idea to also check for `fork` and/or add a setting to _not_
show pages for forks. Or add an `exclude` setting for repos as well?

## Recurse

Although the implementation uses recursion, this feature should have a different
name from this implementation detail.

Maybe `folder_structure`? or `file_structure` or something like
`frontmatter_sort: false`?

## Posts

There should be a way to dipsplay posts:

- Under a "posts" menu item
- Without dates in the menu, as it now looks like this:
  ```
  2020                  ⌄
    2020 07             ⌄
        2020 07 11      ⌄
            First post
  ```

## Add posts to classic nav

It might be possible to add posts to the classic nav using:

```
  {% if site.nav.include_posts %}
  {%- assign ordered_posts_list = site.posts | where_exp:"item", "item.nav_order != nil" -%}
  {%- assign unordered_posts_list = site.posts | where_exp:"item", "item.nav_order == nil" -%}

  {%- assign ordered_pages_list = ordered_pages_list | concat: ordered_posts_list -%}
  {%- assign unordered_pages_list = unordered_pages_list | concat: unordered_posts_list -%}
{% endif %}
```

But then "something" needs to be done with the sort order (i.e. to sort posts by
date rather than by title)
