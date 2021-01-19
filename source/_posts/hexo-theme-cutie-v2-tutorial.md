---
title: hexo theme cutie v2.x tutorial
tags: [hexo, cutie, tutorial]
categories: [notes]
toc_level: 3
version: 3
date: 2018-02-12 00:00:00 Z
---

![cover](images/tree.png)

Theme cutie has evolved from v1.x to v2.x with a refreshed and fine tuned design and more features. Follow the following instruction to install and use it. You may navigate this website to experience the new look and interaction of v2.x.

__Thank you for your stars and support__.

<!-- more -->

# Installation

## Install for a new site

Prerequiste
:   Make sure you install `node.js` and `hexo` through command line. Refer to official Hexo doc for detailed instruction.

Working directory
:   Make sure your terminal (command line) is currently in the folder where you want to create the site.

Installation steps
:   The first step is the standard hexo installation step. If you have done them, skip to step 2.  
    1. Initialize your site
    ```bash
    hexo init your-site-folder
    cd your-site-folder
    npm install
    ```
    2. [_Optional_][_Recommended_] Uninstall `hexo-renderer-marked` and install `hexo-renderer-markdown-it` and associated plugins.
    ```bash
    npm un hexo-renderer-marked --save
    npm i hexo-renderer-markdown-it --save
    npm i markdown-it-emoji --save
    npm i markdown-it-mark --save
    npm i markdown-it-deflist --save
    npm i markdown-it-container --save
    ```

    3. Download [latest theme cutie](https://github.com/qutang/hexo-theme-cutie/releases/latest) and unzip it to `themes/` folder in your site. Then rename it to `cutie`.

Initial configuration file
:   `_config.yml` in the root path of your site.

Initial configuration
:   1. Follow standard hexo initial configuration: https://hexo.io/docs/configuration.html
    2. Add variables or modify the variables in your `_config.yml` according to following snippet.

        ```yml _config.yml
        highlight:
          enable: true
          line_number: true
          auto_detect: false
          tab_replace: 
        markdown:
          render:
            html: true
            xhtmlOut: false
            breaks: false
            linkify: true
            typographer: true
            quotes: '“”‘’'
          plugins:
            - markdown-it-abbr
            - markdown-it-footnote
            - markdown-it-ins
            - markdown-it-sub
            - markdown-it-sup
            - markdown-it-deflist
          anchors:
            level: 1
            collisionSuffix: 'v'
            permalink: false
            permalinkClass: header-anchor
            permalinkSymbol: ""
            permalinkBefore: false
        date_format: ll
        archive_generator:
          per_page: 0
          yearly: true
          monthly: false
          daily: false
        theme: cutie
        ```
Bring site alive
:   ```bash
    hexo s --debug
    ```

## Install for an existing site

Working directory
:   Make sure your terminal (command line) is currently in the root folder of the site.

Installation steps
:
1. [_Optional_][_Recommended_] Uninstall `hexo-renderer-marked` and install `hexo-renderer-markdown-it` and associated plugins.

        ```bash
        npm un hexo-renderer-marked --save
        npm i hexo-renderer-markdown-it --save
        npm i markdown-it-emoji --save
        npm i markdown-it-mark --save
        npm i markdown-it-deflist --save
        npm i markdown-it-container --save
        ```

2. Download [latest theme cutie](https://github.com/qutang/hexo-theme-cutie/releases/latest)
 and unzip it to `themes/` folder in your site. Then rename it to `cutie`.

Initial configuration file
:   `_config.yml` in the root path of your site.

Initial configuration
:   1. Follow standard hexo initial configuration: https://hexo.io/docs/configuration.html
    2. Add variables or modify the variables in your `_config.yml` according to following snippet.

        ```yml _config.yml
        highlight:
          enable: true
          line_number: true
          auto_detect: false
          tab_replace: 
        markdown:
          render:
            html: true
            xhtmlOut: false
            breaks: false
            linkify: true
            typographer: true
            quotes: '“”‘’'
          plugins:
            - markdown-it-abbr
            - markdown-it-footnote
            - markdown-it-ins
            - markdown-it-sub
            - markdown-it-sup
            - markdown-it-deflist
          anchors:
            level: 1
            collisionSuffix: 'v'
            permalink: false
            permalinkClass: header-anchor
            permalinkSymbol: ""
            permalinkBefore: false
        date_format: ll
        archive_generator:
          per_page: 0
          yearly: true
          monthly: false
          daily: false
        theme: cutie
        ```
Bring site alive
:   ```bash
    hexo s --debug
    ```

# Upgrade

## From v2.x

Installation steps
:   1. Delete `themes/cutie/` folder in your site.
    2. Download the desired version of theme cutie from [release page](https://github.com/qutang/hexo-theme-cutie/releases), unzip it to `themes/` folder and rename it to `cutie`.

Notes
:   There is a mimimal version requirement for each configuration, make sure your installed version is above it to use the corresponding configuration.

## From v1.x

Installation steps
:   1. Delete `themes/cutie/` folder in your site.
    2. Download the desired version of theme cutie from [release page](https://github.com/qutang/hexo-theme-cutie/releases), unzip it to `themes/` folder and rename it to `cutie`.

Configuration
:   From v2.x, theme cutie uses _Hexo data file_ (`sources/_data/cutie.yml`) to store all configurations, instead of using the `_config.yml` file of your site in v1.x. And the YAML structure has changed compared to v1.x. 

    The recommendation is to configure the theme cutie from scratch using the following configuration guidelines.

    You may copy or reuse some configurations about theme cutie in your old `_config.yml` along the way. 
    
    Please post an issue if you have hard time migrating your configurations from v1.x to v2.x.

# Configuration

## Language

Minimal version
:   _Taurus_: `v2.0.0-alpha`

Configuration file
:   `_config.yml` of site

Configuration format
:   Set `language` variable in your site's `_config.yml` file.

    ```yml _config.yml
    language:
    - en
    - zh-cn
    - it
    ```
    The first row will be your site's default language.

Default configuration
:   If configuration is omitted, the default setting is `en`. Site will be displayed in English.

Notes
:   Currently, theme cutie only supports three languages: English, Italian and 简体中文.

Contributions
:   1. Italian translation is contributed by [@fastbyte01](https://github.com/Fastbyte01)
    2. More translation is welcomed if you are interested in contribution. You may add new language files in `themes/cutie/languages` folder according to Hexo's guideline: https://hexo.io/docs/internationalization.html and feel free to send me pull request.

## Scheme

This concept is from `hexo-theme-next`, the most popular theme for Hexo, in which it uses different themes for different layout design. In theme cutie, it follows the similar idea and provides the opportunity to choose different layout design using scheme.

Minimal version
:   _Taurus_: `v2.0.0-alpha`

Configuration file
:   `source/_data/cutie.yml`

Configuration format
:   Set `scheme` variable to scheme name to enable a theme scheme.

    ```yml source/_data/cutie.yml
    global:
      scheme: Taurus # Avaliable values: Taurus
    ```

Default configuration
:   If configuration is omitted, the default setting is `Taurus`, scheme `Taurus` is enabled.

Notes
:   Currently, theme cutie only has `Taurus` theme, which is a two-column text-icon-based layout. Contribution is welcomed from developers or designers for new schemes.

For contributors
:   1. To add a new scheme, create a new file `your-scheme-name.css` in folder `themes/cutie/source/css/` and add your own scheme style in it.
    2. The system will automatically search for this css file and load it using the theme name `your-scheme-name` when changing the scheme configuration to `your-scheme-name`.

## Animation

Minimal version
:   `v2.0.5-beta`

Configuration file
:   `source/_data/cutie.yml`

Configuration format
:   Set `use_animation` to `true` or `false` to enable or disable site animations.

    ```yml source/_data/cutie.yml
    global:
      use_animation: true # Avaliable values: true, false
    ```

Default configuration
:   If configuration is omitted, the default setting is `true`, animation is enabled.

## Search

Theme cutie uses in-site search for the site. Use following steps to setup search page. Google custom search has been discarded since `v2.0.7`.

Minimal version
:   `v2.0.7`

Configuration steps
:   1. No need for configuration, work out of box.
    2. If you are upgrading from versions below `v2.0.7`, delete the old search page you created for your site.

## 404 Page

Theme cutie uses built-in 404 page. It supports a custom 404 art or tencent 404 charity page (腾讯404公益).

Minimal version
:   `v2.0.7`

Configuration file
:   `source/_data/cutie.yml`

Configuration steps
:   1. Delete the old `404.md` file of your site if you are upgrading from versions before `v2.0.7`.
    2. No need for configuration, work out of box. 
    3. You may configure the built-in 404 page to use 腾讯公益404 or not, by default it is NOT using 腾讯公益404.

    ```yml source/_data/cutie.yml
    # set true to enable 腾讯公益404
    page_404:
      tencent_404: true
    ```

## Social network links

Minimal version
:   `v2.0.0-alpha`

Configuration file
:   `source/_data/cutie.yml`

Configuration format
:   Add social network names and links in the following format. Make sure the social network name matches the corresponding font awesome icon name. See [here](https://fontawesome.com/icons?d=gallery&s=brands) for the supported names and their icons.

    ```yml source/_data/cutie.yml
    # As long as the name matches the font awesome icon name, you can add even more social links
    social:
      github: https://github.com/qutang
      linkedin: https://www.linkedin.com/in/qutang
    ```

Default configuration
:   If configuration is omitted. No icons will be shown at the bottom right corner in the footer.

## Site announcement

Minimal version
:   `v2.0.7`

Configuration file
:   `source/_data/cutie.yml`

Configuration steps
:   1. Site announcement will display at the bottom left corner of home page as a purple box.
    2. Add following snippets to the configuration file to use, if omitted, site announcement is disabled.

    ```yml source/_data/cutie.yml
    global:
      announcement:
        text: This is a sample site announcement.
    ```

Notes
:   * The timeout duration for site announcement is 10s. The announcement popup will dismiss on click or on timeout.
    * You may use HTML markups in the announcement text. For example, you may add a link to the text.

## Site header

### Setup site logo

Minimal version
:   `v2.0.0-alpha`

Configuration file
:   `sources/_data/cutie.yml`

Configuration format
:   Set variable `logo` to your own icon's link. Link can be either an external image link, or a relative link.

    ```yml source/_data/cutie.yml
    logo: /images/logo.svg
    ```

Default configuration
:   If configuration is omitted. the following image will be used as the logo image.

    ![theme-icon](/images/logo.svg)

### Setup site name and subtitle

Minimal version
:   `v2.0.0-alpha`

Configuration file
:   `_config.yml` of your site

Configuration format
:   Make sure your subtitle is not too log (better less than 30 characters).

    `title` is a standard Hexo configuration.
    `subtitle` is theme cutie's own configuration.

    ```yml source/_data/cutie.yml
    title: Your site's title
    subtitle: Your site's subtitle
    ```

Default configuration
:   If configuration is omitted. You will not see any texts in the header.

Note
:   This configuration requires restarting the server.

### Setup navigation menu

Minimal version
:   `v2.0.0-alpha`

Configuration file
:   `sources/_data/cutie.yml`

Configuration format
:   Add navigation item in the following format. link and icon can be external or internal. You can literally add any link to it.

    ```yml source/_data/cutie.yml
    menu:
      Resume: 
        link: /resume/
      "Menu item":
        link: /aaa/
    ```

Default configuration
:   If configuration is omitted. No text links will show up in the header navigation menu or in the dropdown menu on any view.

Notes
:   1. If there are more than four menu items, only the first four will be shown in the header (on desktop view). However, you can find all menu items in the last dropdown menu.
    2. Do not use a very long menu item name. No more than three words, because there is some display issue when the name gets long.
    3. Compared with `v1.x`, menu icon is no longer supported.

## Post

### Use Light Gallery

Theme cutie uses [Light Gallery]() to support image modal display for _posts_. By default, it is enabled, but if you want to use other hexo plugins with similar functionality, you may want to disable it.

Minimal version
: `v2.0.5-beta`

Configuration file
: `source/_data/cutie.yml`

Configuration format
:   Set `use_lightgallery` to be `true` or `false` to enable or disable light gallery display for post images.

    ```yml source/_data/cutie.yml
    post:
      use_lightgallery: true
    ```

Default configuration
:   If configuration is omitted, by default light gallery is enabled for all posts.

Notes
:   It is currently not supported to enable or disable light gallery for an individual post.

### Use post version

Theme cutie supports versioned post. Whenever the content of your post changes after you push your site, your visitors will see an unread badge on the post card in home page and archive pages.

Theme cutie uses Hashing and Cookie to track the post content change and the post content a visitor has last read. This feature does NOT use `leancloud` backend.

Minimal version
: `v2.0.8`

#### For all posts

Configuration file
: `source/_data/cutie.yml`

Configuration format
:   Set `enable_unread_badge` to be `true` to enable post versioning and unread badge or `false` to disable this feature for all the posts.

    ```yml source/_data/cutie.yml
    ---
    post:
      enable_unread_badge: false
    ---
    ```

Default configuration
:   If configuration is omitted, by default this feature is __disabled__ for all posts.

#### For an individual post

Configuration file
: A post's front matter

Configuration format
:   Set `enable_unread_badge` to be `true` to enable post versioning and unread badge or `false` to disable this feature for the individual post.

    ```yml post's front matter
    ---
    enable_unread_badge: true
    ---
    ```

Default configuration
:   If configuration is omitted, the setting will roll back to the unread badge setting for all the posts.

Notes
:   This setting has higher priority than the setting for all the posts.

### Setup TOC level
*[TOC]: Table of content

Minimal version
: `v2.0.5-beta`

#### For all posts

Configuration file
: `source/_data/cutie.yml`

Configuration format
:   Set `toc_level` under `post` to set the maximum level of headings in TOC for _all posts_. Allowed value is from `1` to `6`.

    ```yml source/_data/cutie.yml
    post:
      toc_level: 2
    ```

Default configuration
:  If this configuration is omitted, by default maximum TOC level is set to 2 (meaning `##` in markdown).

#### For an individual post

Configuration file
:  A post's front matter

Configuration format
:   Use variable `toc_level` to set the maximum level of headings in TOC for _an individual posts_. Allowed value is from `1` to `6`.

    ```yml
    ---
    toc_level: 2
    ---
    ```

Default configuration
:   If variable is omitted in the post front matter, setting will fall back to the [all-post-toc-setting](#for-all-posts).

### Setup post comment

Minimal version
:   `v2.0.5-beta`

#### For all posts

Configuration file
: `source/_data/cutie.yml`

Configuration format
:   Set `allow_comment` to be `true` or `false` to enable or disable comment section to be displayed for _all posts_.

    ```yml source/_data/cutie.yml
    post:
      allow_comment: true
    ```

Default configuration
:  If this configuration is omitted, by default comment section is enabled for all posts.

#### For an individual post

Configuration file
:  A post's front matter

Configuration format
:   Use variable `allow_comment` to enable or disable comment section.

    ```yml
    ---
    allow_comment: true
    ---
    ```

Default configuration
:   If variable is omitted in the post front matter, setting will fall back to the [all-post-comment-setting](#for-all-posts-v2).

### Setup post copyright

Minimal version
:   `v2.0.5-beta`

Theme cutie uses Creative Commons licenses for copyright configuration. We use three nested variables to cover the major licenses in Creative Commons.

* `allow_share`: allow post to be shared (`true`) or not (`false`).
    * `allow_modification`: allow post to be modified while sharing when `true`.
    * `allow_commercial`: allow post to be used for commercial purpose while sharing when `true`.

if `allow_share` is `false`, the other two variables will be ignored.

#### For all posts

Configuration file
: `source/_data/cutie.yml`

Configuration format
:   Use the three variables under `post` to configure the all-post copyright setting.

    ```yml source/_data/cutie.yml
    post:
      allow_share: true
      allow_modification: false
      allow_commercial: false
    ```

Default configuration
:   If any of these configurations is omitted, the default setting for each one will fall back to following settings,
    * `allow_share: true`, by default allowing sharing all posts.
        * `allow_modification: false`, by default post is not allowed to be modified while sharing.
        * `allow_commercial: false`, by default post is not allowed to be used for commercial purposes while sharing.
    
    The corresponding default Creative Commons license is _CC BY-NC-ND 4.0_.

#### For an individual post

Configuration file
:  A post's front matter

Configuration format
:   Use the same three variables to configure copyright setting for a specific post.

    ```yml
    ---
    allow_share: true
    allow_modification: false
    allow_commercial: false
    ---
    ```

Default configuration
:   If any of these variables is omitted in the post front matter, setting will fall back to the [all-post copyright setting](#for-all-posts-v3).

### Enable post visit and comment counts

Minimal version
:   `v2.0.5-beta`

Prerequiste
:   This functionality only works when you use `valine` as [comment system](#comment-systems) and use `leancloud` as backend.

Configuration steps
:   1. Configure `valine` comment system as described [here](#configuration-for-valine-comment-system).
    2. You are all set and post visit counts and post comment counts will appear in all related pages.

Notes
:   * _If backend is not set up properly, icons that show post visit and comment counts will be hidden._
    * Post visit counts only __unique__ visitors (meaning visitors with unique IPs).

### Enable post thumb up

Minimal version
:   `v2.1.0`

Prerequiste
:   This functionality only works when you use `valine` as [comment system](#comment-systems) and use `leancloud` as backend.

Configuration steps
:   1. Configure `valine` comment system as described [here](#configuration-for-valine-comment-system).
    2. You are all set and post thumb up and thumb up counts will appear in all related pages.

Notes
:   * _If backend is not set up properly, icons that show post thumbup status and counts will be hidden._
    * Post thumb up counts only __unique__ visitors (meaning visitors with unique IPs).

### Use post announcement

Minimal version
:   `v2.0.7`

Configuration file
:   post's front matter

Configuration steps
:   Use following snippet to add your post annoucement

    ```yml post's front matter
    ---
    announcement:
      text: This is a sample post announcement!
    ---
    ```

Notes
:   * The default timeout for the announcement is 10 seconds. Note configurable for now.
    * You may use HTML markups in the announcement text.

### Set post excerpt

The post excerpt, displayed in the index page card on hover, may be manually set through front matter or adding the `<!-- more -->` tag plugin in the post.

Minimal version
:   `v2.0.11`

Configuration file
:   post's front matter, or tag plugin

Configuration waterfall
:   `abstract` variable in the front matter has the highest priority if set.

    ```yml post's front matter
    ---
    abstract: A sample excerpt.
    ---
    ```

    If `abstract` is not set, theme cutie will search `<!-- more -->` tag in the post content to identify the excerpt section and cut off the first 150 characters to be used as excerpt.

    If both `abstract` and `<!-- more -->` are omitted, theme cutie will automatically chunk the first 150 characters in the post content to be used as excerpt.

### Set post icon

The post icon, displayed on the top left cornder of the index page card, may be manually set through front matter in the post.

Minimal version
:   `v2.0.0`

Configuration file
:   post's front matter

Configuration waterfall
:   If `icon` variable in the post front matter is set, the system will use this icon for post.

    ```yml post's front matter
    ---
    icon: /your/post/icon/path
    ---
    ```

    I recommend you to use absolute path (starting with `/`) for the image path.

    If `icon` variable is not set, but post belongs to category `notes` or `projects`, the system will use the default category icon for the post.

    If both conditions are not satisified, the system will use a randomly generated texture image for the post.

## Icon sets

### Select an icon set

Minimal version
:   `v2.0.5-beta`

Configuration file
: `source/_data/cutie.yml`

Configuration format
:   Change icon set by changing the name of the icon set in the following snippet. There are three available icon sets in the theme by default: `blue-line`, `blue-shadow`, and `colorful-outlined`.

    ```yml source/_data/cutie.yml
    global:
      icon_set: blue-line # Available values in theme: blue-line, blue-shadow, colorful-outlined
    ```
Default configuration
: `blue-line`

Illustration

### Add a new icon set

Minimal version
:   `v2.0.5-beta`

Configuration path
: `source/images/`

Configuration steps
:   1. Create a folder named `icons` in `source/images/` folder.
    2. Create an icon set folder `icon-set-name`(change it to your desired name) in `source/images/icons/` folder.
    3. Add your own four icons (keep the filename consistent) in `svg` format to `source/images/icons/icon-set-name/` folder.
        1. `search.svg`
        2. `archive.svg`
        3. `menu.svg`
        4. `toc.svg`
    4. Use your new icon set name `icon-set-name` in [Select an existing icon set](#select-an-existing-icon-set)

## Comment systems

### Select comment systems

Minimal version
:   `v2.0.0-alpha`

User configuration location
: `source/_data/cutie.yml`

Configuration format
:   ```yml comment system
    global:
      comment_system: valine # Available values: valine, gitment, disqus
    ```

Possible values
:   `valine`(default), `gitment`, `disqus`, `livere`

After selecting one of the comment systems, you need to further configure it.

### Configuration for valine comment system

Minimal version
:   `v2.0.0-alpha`

User configuration location
: `source/_data/cutie.yml`

Configuration format
:   ```yml valine configuration
    valine:
      appId:
      appKey:
      placeholder:
    ```
    See https://valine.js.org to setup the backend and fill the values.

Default values
: No default values, must fill if using the system.

### Configuration for gitment comment system

Minimal version
:   `v2.0.0-alpha`

User configuration location
: `source/_data/cutie.yml`

Configuration format
:   ```yml gitment configuration
    gitment:
      owner:
      repo:
      client_id:
      client_secret:
    ```
    See https://github.com/imsun/gitment to setup the backend and fill the values.

Default values
: No default values, must fill if using the system.

### Configuration for Disqus comment system

Minimal version
:   `v2.0.0-alpha`

User configuration location
: `source/_data/cutie.yml`

Configuration format
:   ```yml disqus configuration
    disqus:
      shortname:
    ```
    See https://help.disqus.com/customer/portal/articles/466208-what-s-a-shortname- to setup the backend and fill the value.

Default values
: No default values, must fill if using the system.

### Configuration for Livere comment system

Minimal version
:   `v2.0.11`

User configuration location
: `source/_data/cutie.yml`

Configuration format
:   ```yml livere configuration
    livere:
      id: 'city' # use 'city' if using free version or `premium` if using paid version
      uid: 
    ```
    The `uid` is the string you will see in the snippet provided by livere during installation, as shown in the following screenshot.
    
    ![Livere setup screenshot](livere_setup.png)

Default values
: No default values, must fill if using the system.


## Math Test
{% mathjax %}
$\gamma = \cfrac{1}{n_{jm}} \sum_{x_i \in R_{i,j}}y_i - F_{m-1}(x_i)$
{% endmathjax %}
