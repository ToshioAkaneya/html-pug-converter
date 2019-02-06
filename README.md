# html-pug-converter
Converts **HTML** to **Pug** templating language (_formerly Jade_).  
Requires Node.js version `7.6` or higher.

Turns this :unamused:
```html
<!doctype html>
<html lang="en">
  <head>
    <title>Hello World!</title>
  </head>
  <body>
    <div id="content">
      <h1 class="title">Hello World!</h1>
    </div>
  </body>
</html>
```

Into this :tada:
```pug
doctype html
html(lang='en')
  head
    title Hello World!
   body
    #content
      h1.title Hello World!
```

## Install

Get it on [npm](https://www.npmjs.com/package/html-pug-converter):

```bash
npm i -g html-pug-converter
```

## Usage

### CLI
Accept input from a file and write to stdout:

```bash
html-pug-converter < example.html
```

Or write to a file:
```bash
html-pug-converter < example.html > example.pug
```

See `html-pug-converter --help` for more information.

### Programmatically

```js
const htmlPugConverter = require('html-pug-converter')

const html = '<header><h1 class="title">Hello World!</h1></header>'
const pug = htmlPugConverter(html, { tabs: true })
```

### Options

Name | Type | Default | Description
--- | --- | --- | ---
tabs | Boolean | `false` | Use tabs instead of spaces
fragment | Boolean | `false` | Wrap in enclosing `<html>` and `<body>` tags
