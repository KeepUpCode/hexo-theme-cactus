# Cactus

A responsive, clean and simple [Hexo](http://hexo.io) theme for a personal website.

:cactus: [Demo](https://probberechts.github.io/hexo-theme-cactus/)

![screenshot](https://docs.google.com/uc?id=1K66bccwr4z9TgJev0AzCqbI7BxzVr7md)

## Summary

- [General](#general)
- [Features](#features)
- [Install](#install)
- [Configuration](#configuration)
- [License](#license)

## General

- **Version** : 3.0
- **Compatibility** : Hexo 3 or later

## Features

- Fully responsive
- Multiple color schemes
- Pick your own code highlighting scheme
- Configurable navigation menu
- Support for local search
- Projects list
- I18n support
- Disqus integration
- Google analytics / Baidu Tongji
- Font Awesome icons
- Simplicity

## Install
1. In the `root` directory:

    ```git
    $ git clone https://github.com/probberechts/hexo-theme-cactus.git themes/cactus
    ```

2. Change the `theme` property in the `config.yml` file.

    ```yml
    # theme: landscape
    theme: cactus
    ```

3. Run: `hexo generate` and `hexo server`


## Configuration
You can (and should) modify a couple of settings. An overview of all settings
can be found in  [_config.yml](_config.yml). The most important ones are
discussed below.

There are two possible methods to override these variables. As a first option,
you could fork the theme and maintain a custom branch with your settings.
Alternatively, you can configure it from your site's primary configuration
file. Therefore, define you custom settings under the `theme_config` variable.
For example:

```yml
# _config.yml
theme_config:
  colorscheme: white
```


```yml
# themes/cactus/_config.yml
colorscheme: dark
```

This will result in the white color scheme.


### Color scheme

Currently, this theme is delivered with four color schemes: [dark](https://probberechts.github.io/hexo-theme-cactus/cactus-dark/public/), [light](https://probberechts.github.io/hexo-theme-cactus/cactus-light/public/),
[white](https://probberechts.github.io/hexo-theme-cactus/cactus-white/public/) and [classic](https://probberechts.github.io/hexo-theme-cactus/cactus-classic/public/). Set your preferred color scheme in the `_config.yml` file.

```yml
colorscheme: light
```

Alternatively, you can easily create your own color scheme by creating a new
file in `source/css/_colors`.


### Navigation

Setup the navigation menu in the `_config.yml`:

```yml
nav:
  Home: /
  About: /about/
  Writing: /archives/
  Projects: http://github.com/probberechts
  LINK_NAME: URL
```


### Blog posts list on home page

You have two options for the list of blog posts on the home page:

  - Show only the 5 most recent posts (default)

    ```yml
    posts_overview:
      show_all_posts: false
      post_count: 5
    ```

  - Show all posts

    ```yml
    posts_overview:
      show_all_posts: true
    ```


### Projects list

Create a projects file `source/_data/projects.json` to show a list of your projects on the index page.

```json
[
    {
       "name":"Hexo",
       "url":"https://hexo.io/",
       "desc":"A fast, simple & powerful blog framework"
    },
    {
       "name":"Font Awesome",
       "url":"http://fontawesome.io/",
       "desc":"The iconic font and CSS toolkit"
    }
]
```


### Social media links

Cactus can automatically add links to your social media accounts.
Therefore, update the theme's `_config.yml`:

```yml
social_links:
  github: your-github-url
  twitter: your-twitter-url
  NAME: your-NAME-url
```

where `NAME` is the name of a [Font Awesome icon](https://fontawesome.com/icons?d=gallery&s=brands).


### Language configuration

If you are new to Hexo and internationalization (i18n), please read
[Hexo documentation - internationalization (i18n) section](https://hexo.io/docs/internationalization.html)

Currently, the theme is delivered with support for:

- English (en), default
- Chinese (Simplified, PRC) (zh-CN)
- French (fr)
- Dutch (nl)
- Spanish (es)
- Russian (ru)

If you would like to use one the languages listed above, simply set `language`
to the desired language (e.g., `fr`) in `_config.yml`.
Otherwise, you can follow the steps below (E.g., to add a Japanese (ja) translation):

1. Set `language` to `ja` in Hexo configuration file `_config.yml`
2. Create a `ja.yml` file in the `themes/cactus/languages/` folder
3. Copy the content of `themes/cactus/languages/default.yml` and paste it it into the `ja.yml` file
4. Replace all English strings by their Japanese translation

**Note: Cactus does not support multi-language sites.**


### RSS

Set the `rss` field in the `_config.yml` to one of the following values:

1. `rss: false` will totally disable rss (default).
2. `rss: atom.xml` sets a specific feed link.
3. `rss:`leave empty to use the [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) plugin.


### Analytics

Add you Google Analytics or Baidu Tongji `tracking_id` to the `_config.yml`.

```yml
google_analytics:
  enabled: true
  id: 'UA-49627206-1'

baidu_analytics:
  enabled: true
  id: 2e6da3c375c8a87f5b664cea6d4cb29c
```


### Comments

First, create a site on Disqus: [https://disqus.com/admin/create/](http://disqus.com/admin/create/).

Next, update the `_config.yml` file:

```yml
disqus:
  enabled: true
  shortname: SITENAME
```

where `SITENAME` is the name you gave your site on Disqus.


### Code Highlighting

Pick one of [the available colorschemes](https://github.com/probberechts/hexo-theme-cactus/tree/master/source/css/_highlight) and add it to the `_config.yml`:

```yml
highlight: COLORSCHEME_NAME
```


### Local search

First, install the [hexo-generate-search](https://www.npmjs.com/package/hexo-generator-search)
plugin, which will generate a search index file.

```git
$ npm install hexo-generator-search --save
```

Next, create a page to display the search engine:

```sh
$ hexo new page Search
```
and put `search: true` in the front-matter.

Finally, edit the `_config.yml` and add a link to the navigation menu.

```yml
nav:
  search: /Search/
```


## License
MIT
