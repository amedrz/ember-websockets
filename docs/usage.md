## Simple example of using it in your app

The first thing you must do is import the mixin that ships with
ember-websockets on any **ROUTE** that you would like to use
websockets with. Here is an example of that now:

```js
import socketMixin from 'ember-websockets/mixins/sockets';

export default Ember.Route.extend(socketMixin, {
  socketURL: 'ws://localhost:8080'
});
```

Next set up any actions on your controller which you want handle:

```js
export default Ember.Controller.extend({
  actions: {
    onopen: function(socketEvent) {
      console.log('On open has been called!');
    },
    onmessage: function(socketEvent) {
      console.log('On message has been called!');
    }
  }
});
```
