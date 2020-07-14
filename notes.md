# Development notes and general ideas

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
