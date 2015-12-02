# markdown-it-alerts
[Markdown-it][markdown-it] plugin to create [Bootstrap alerts][bootstrap-alerts].

E.g.:

```md
::: warning
Hello world! [Link](#).
:::
```

Gets converted to:

```html
<div class="alert alert-warning" role="alert">
<p>Hello world! <a href="#" class="alert-link">Link</a>.</p>
</div>
```


## Install

```bash
$ npm install markdown-it-alerts --save
```



## Usage


### Enable plugin

```js
var md = require('markdown-it');
var alerts = require('markdown-it-alerts');

md().use(alerts);
```


### Options

Enable/disable adding class `alert-link` to links inside alerts.

```js
var md = require('markdown-it');
var alerts = require('markdown-it-alerts');

md().use(alerts, {links: false});
```


### Example

With option `links` enabled (by default):

```md
This is a test. [Link](#).

::: success
Hello world! [Link](#).
:::

This is a test. [Link](#).
```

Gets converted to:

```html
<p>This is a test. <a href="#">Link</a>.</p>
<div class="alert alert-success" role="alert">
<p>Hello world! <a href="#" class="alert-link">Link</a>.</p>
</div>
<p>This is a test. <a href="#">Link</a>.</p>
```


[markdown-it]: https://github.com/markdown-it/markdown-it
[bootstrap-alerts]: http://getbootstrap.com/components/#alerts