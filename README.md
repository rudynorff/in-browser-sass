# in-browser-sass

Compile SASS / SCSS in the browser.

[Japanese version is here](README.ja.md)


## Installation

```html
<!-- Load sass.js -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/sass.js/0.10.7/sass.sync.min.js"></script>
<!-- Load this script -->
<script src="in-browser-sass.js"></script>
```

[sass.js](https://github.com/medialize/sass.js) CDNs are available here:

- https://cdnjs.cloudflare.com/ajax/libs/sass.js/0.10.7/sass.sync.min.js
- https://unpkg.com/sass.js@0.10.7/dist/sass.sync.js


## Usage

You can use `link` or `style` elements for include SASS / SCSS. `type="text/sass"` or `type="text/sass"` attribute must be set.

```html
<!-- SASS : link tag -->
<link rel="stylesheet" type="text/sass" href="example.sass">

<!-- SCSS : link tag -->
<link rel="stylesheet" type="text/scss" href="example.scss">

<!-- SASS : style tag -->
<style type="text/sass">
body
  p
color: #f00
</style>

<!-- SCSS : style tag -->
<style type="text/scss">
body {
  p {
font-weight: bold;
  }
}
</style>
```

This compiles to:

```html
<!-- SASS : link tag -->
<link rel="stylesheet" type="text/sass" href="example.sass">
<!-- Compiled example.sass -->
<style type="text/css">
body > selection {
  font-size: 110%;
}
</style>

<!-- SCSS : link tag -->
<link rel="stylesheet" type="text/scss" href="example.scss">
<!-- Compiled example.scss -->
<style type="text/css">
a {
  color: #06f;
}
a:hover {
  color: #f09;
}
</style>

<!-- SASS : style tag -->
<style type="text/sass">
body
  p
color: #f00
</style>
<!-- Compiled inline SASS -->
<style type="text/css">
body p {
  color: #ff0;
}
</style>

<!-- SCSS : style tag -->
<style type="text/scss">
body {
  p {
font-weight: bold;
  }
}
</style>
<!-- Compiled inline SCSS -->
<style type="text/css">
body p {
  font-weight: bold;
}
</style>
```

Compiled `style` elements are inserted after each original element.


## Author

[Neo](http://neo.s21.xrea.com/) ([@Neos21](https://twitter.com/neos21))

- [GitHub - in-browser-sass](https://github.com/Neos21GitHub/in-browser-sass)