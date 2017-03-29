# RESTful API Test Components powered by Polymer

This project is based on Polymer 2.0

[Demo Here](https://hectorguo.com/smartcar-component)

## Usage

### `app.html`

```html
<link rel="import" href="https://polygit.org/polymer+2.0.0-rc.2/components/polymer/polymer-element.html">
<link rel="import" href="smartcar-api.html">

<dom-module id="app">
  <template>
    <smartcar-api request="[[reqOption]]"></smartcar-api>
  </template>
</dom-module>

<script>
  class App extends Polymer.Element {
      static get is() { return 'app'; }
      constructor() {
        super();
        
        this.reqOption = {
          url: 'https://jsonplaceholder.typicode.com/posts/1/comments',
          method: 'GET',
          headers: {
            Charset: 'UTF-8',
          },
        }
      }
    }

    window.customElements.define(App.is, App);
</script>
```

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <script src="https://polygit.org/webcomponentsjs+1.0.0-rc.5/components/webcomponentsjs/webcomponents-loader.js"></script>
    <link rel="import" href="app.html">
  </head>
  <body>
    <app></app>
  </body>
</html>
```

## Install

I use [Polymer-cli](https://www.polymer-project.org/2.0/docs/tools/polymer-cli) to build and server the project.