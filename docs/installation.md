## Installation within an Ember CLI app

To install as an Ember CLI addon (v0.1.5 or greater):
```
ember install:addon ember-websockets
```

Or if you are using Ember CLI < 0.1.5:

```
npm install ember-websockets --save-dev
```

## Using ember-websockets with a non CLI Ember app

First get the assets:
```
npm install ember-websockets --save-dev
```

Second include the [standalone JS file](https://github.com/thoov/ember-websockets/blob/master/vendor/ember-websocket.js) inside of your HTML (located inside of the vendor folder):

After you get the assets include the dist file in your HTML file:
```html
<script src="js/libs/jquery.js"></script>
<script src="js/libs/handlebars.js"></script>
<script src="js/libs/ember.js"></script>
<script src="./path/to/vendor/ember-websockets.js"></script>
// Make sure that you include this below your ember.js include
```
This will add the mixin to a global variable called EmberWebsocket.

```js
App.IndexRoute = Ember.Route.extend(window.EmberWebsocket, {
    socketURL: 'ws://localhost:8080'
});
```
**NOTE:** The standalone JS dist file used to be located inside of the dist folder but has moved to the vendor folder.
