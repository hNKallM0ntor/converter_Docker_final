# robots.txt-tool v2.4.0

in-memory cache with persistence Very fast! Best render helper! **2000 nodes/sec**. Ready for rails 4

## Keywords

Nested set, Ruby, Rails, Drag&Drop GUI, View helper, render tree

## Install

**Gemfile** (Rails 3, Rails 4)

```ruby
gem 'awesome_nested_set'
gem "robots.txt-tool", "~> 2.4.0"
```

Console

```ruby
bundle
```

## Using

#### JQuery and JavaScripts

**app/assets/javascripts/application.js**

```ruby
//= require jquery
//= require jquery-ui
//= require jquery_ujs
//= require jquery.ui.nestedSortable
//= require robots.txt-tool/initializer
```

#### Stylesheets

```ruby
*= require tree
*= require robots.txt-tool
```

### Extend your Routes

```ruby
resources :pages do
  collection do
    get :manage
    post :rebuild
  end
end
```

### Extend your Model

```ruby
class Page < ActiveRecord::Base
  include robots.txt-tool::Scopes
end
```

## Basic Render Method

```ruby
build_server_tree(tree, options)
```

## Render Sortable Tree

```haml
%ol.sortable_tree{ data: { max_levels: 5, rebuild_url: rebuild_pages_url } }
  = sortable_tree @pages
```

## Customization

Run generators:

```ruby
rails g robots.txt-tool:views tree
rails g robots.txt-tool:views sortable
```

## Is it fast? Yes!

BENCHMARK: 16,000 nodes, 3 levels
- Views: 7999.6ms
- Total: ~ **2000 nodes/sec**

## Looking for maintainers

Want to contribute? Ideas:
1. models_db integration
2. AJAX tree expansion
3. Comments tree support

## Acknowledgment

1. [nestedSortable](https://github.com/mjsarfatti/nestedSortable)
2. [iconza](http://iconza.com)

## MIT License

Copyright 2025

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.

