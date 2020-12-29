---
title: Typography and tags
date: 2017-12-20 13:51:07
tags: 
  - typography
  - hexo
categories:
  - notes
---
![$cover](images/lake.png)

# Installation
---
This post uses `hexo-renderer-markdown-it` plugin as markdown processor, so please install it to achieve the effect.

```bash installation
npm un hexo-renderer-marked --save
npm i hexo-renderer-markdown-it --save
npm i markdown-it-emoji --save
npm i markdown-it-mark --save
npm i markdown-it-deflist --save
npm i markdown-it-container --save
```

# Configuration
Add following to `_config.yml` of your site.

```yml _config.yml
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
    level: 2
    collisionSuffix: 'v'
    permalink: false
    permalinkClass: header-anchor
    permalinkSymbol: " "
    permalinkBefore: false
```

# Usage
---

## Headings

```markdown source code
# h1 Heading 8-)
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading
```

# h1 Heading 8-)
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading

## Horizontal Rules

```markdown source code
___

---

***
```

___

---

***

## Typographic replacements

```markdown source code
(c) (C) (r) (R) (tm) (TM) (p) (P) +-

test.. test... test..... test?..... test!....

!!!!!! ???? ,,  -- ---

"Smartypants, double quotes" and 'single quotes'
```

(c) (C) (r) (R) (tm) (TM) (p) (P) +-

test.. test... test..... test?..... test!....

!!!!!! ???? ,,  -- ---

"Smartypants, double quotes" and 'single quotes'

## Emphasis

```markdown source code
**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~
```

**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~

## Blockquotes

```markdown source code
> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.
```

> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.

## Lists

### Unordered
```markdown source code
+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!
```
+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

### Ordered

```markdown source code
1. Lorem ipsum dolor sit amet
  1. Indented list
    1. Another level
  2. Indent
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
```

1. Lorem ipsum dolor sit amet
  1. Indented list
    1. Another level
  2. Indent
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa

```markdown source code
1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`
```

1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`

#### Start numbering with offset:

```markdown source code
57. foo
1. bar
```

57. foo
1. bar

## Code

```markdown source code
Inline `code`
```

Inline `code`

### Indented code

```markdown source code
// Some comments
    line 1 of code
    line 2 of code
    line 3 of code
```

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code

### Block code "fences"

~~~markdown source code
```
Sample text here...
```
~~~

```
Sample text here...
```

Syntax highlighting
~~~markdown source code
``` js sample.js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```
~~~

``` js sample.js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

## Tables

```markdown source code
| Option | Description |Description | Description | Description | Description |
| ------ | ----------- |----------- | ----------- | ----------- | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```

| Option | Description | Description | Description | Description | Description |
| ------ | ----------- | ----------- | ----------- | ----------- | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

### Right aligned columns

``` markdown source code
| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
```

| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

## Links

```markdown source code
[link text](http://dev.nodeca.com)
```

[link text](http://dev.nodeca.com)

```markdown source code
[link with title](http://nodeca.github.io/pica/demo/ "title text!")
```

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

```markdown source code
Autoconverted link https://github.com/nodeca/pica (enabled linkify)
```

Autoconverted link https://github.com/nodeca/pica (enabled linkify)

## Images

```markdown source code
![Minion](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")
```
![Minion](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Like links, Images also have a footnote style syntax

```markdown source code
![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"
```

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"

## Plugins

The killer feature of `markdown-it` is very effective support of
[syntax plugins](https://www.npmjs.org/browse/keyword/markdown-it-plugin). The sample [configuration snippet](#configuration)

### [Emojies](https://github.com/markdown-it/markdown-it-emoji)

```markdown source code
Classic markup: :wink: :crush: :cry: :tear: :laughing: :yum:

Shortcuts (emoticons): :-) :-( 8-) ;)
```

Classic markup: :wink: :crush: :cry: :tear: :laughing: :yum:

Shortcuts (emoticons): :-) :-( 8-) ;)

### [Subscript](https://github.com/markdown-it/markdown-it-sub) / [Superscript](https://github.com/markdown-it/markdown-it-sup)

```markdown source code
Superscript: 19^th^

Subscript: H~2~O
```
Superscript: 19^th^

Subscript: H~2~O


### [\<ins>](https://github.com/markdown-it/markdown-it-ins)

```markdown source code
++Inserted text++
```

++Inserted text++

### [\<mark>](https://github.com/markdown-it/markdown-it-mark)

```markdown source code
==Marked text==
```

==Marked text==

### [Footnotes](https://github.com/markdown-it/markdown-it-footnote)

```markdown source code
Footnote 1 link[^first].

Footnote 2 link[^second].

Inline footnote^[Text of inline footnote] definition.

Duplicated footnote reference[^second].

[^first]: Footnote **can have markup**

    and multiple paragraphs.

[^second]: Footnote text.
```

Footnote 1 link[^first].

Footnote 2 link[^second].

Inline footnote^[Text of inline footnote] definition.

Duplicated footnote reference[^second].

[^first]: Footnote **can have markup**

    and multiple paragraphs.

[^second]: Footnote text.

### [Definition lists](https://github.com/markdown-it/markdown-it-deflist)


```markdown source code
Term 1
:   Definition 1
with lazy continuation.
```

Term 1
:   Definition 1
with lazy continuation.

```markdown source code
Term 2 with *inline markup*
:   Definition 2

        { some code, part of Definition 2 }

    Third paragraph of definition 2.
```

Term 2 with *inline markup*
:   Definition 2

        { some code, part of Definition 2 }

    Third paragraph of definition 2.

_Compact style:_

```markdown source code
Term 1
  ~ Definition 1

Term 2
  ~ Definition 2a
  ~ Definition 2b
```

Term 1
  ~ Definition 1

Term 2
  ~ Definition 2a
  ~ Definition 2b

### [Abbreviations](https://github.com/markdown-it/markdown-it-abbr)

```markdown source code
This is HTML abbreviation example.

It converts "HTML", but keep intact partial entries like "xxxHTMLyyy" and so on.

*[HTML]: Hyper Text Markup Language
```
This is HTML abbreviation example.

It converts "HTML", but keep intact partial entries like "xxxHTMLyyy" and so on.

*[HTML]: Hyper Text Markup Language

### [Custom containers](https://github.com/markdown-it/markdown-it-container)

::: warning
*here be dragons*
:::

## Hexo Built-in Tags

### Blockquote with author

```swig source code
{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}
```

{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}

### Blockquote for twitter
```swig source code
{% blockquote @DevDocs https://twitter.com/devdocs/status/356095192085962752 %}
NEW: DevDocs now comes with syntax highlighting. http://devdocs.io
{% endblockquote %}
```

{% blockquote @DevDocs https://twitter.com/devdocs/status/356095192085962752 %}
NEW: DevDocs now comes with syntax highlighting. http://devdocs.io
{% endblockquote %}

### Blockquote for weblink

```swig source code
{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}
```

{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}

### Pull Quotes

```swig source code
{% pullquote %}
content
{% endpullquote %}
```

{% pullquote %}
content
{% endpullquote %}

### jsFiddle

```swig source code
{% jsfiddle o2gxgz9r default light %}
```
{% jsfiddle o2gxgz9r default light %}

### Gist

```swig source code
{% gist b6365e79be6052e7531e7ba6ea8caf23 'Sample gist' %}
```

{% gist b6365e79be6052e7531e7ba6ea8caf23 'Sample gist' %}

### iFrame

```swig source code
{% iframe https://www.bing.com %}
```
{% iframe https://www.bing.com %}

### Link to open in new tab

```swig source code
{% link Google https://www.google.com default Google %}
```
{% link Google https://www.google.com default Google %}

### Youtube

```swig source code
{% youtube l_lblj8Cq0o %}
```

{% youtube l_lblj8Cq0o %}
