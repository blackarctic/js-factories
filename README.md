# JS Factories 

A reference for creating factories that create objects in JavaScript.

I have found this to work quite well for most applications.


### Define

```js
let ThingFactory;

ThingFactory = (function () {
    let thing = {};

    thing.copy = function (otherThing) {
        this.attr = otherThing.attr;
        return this;
    };

    thing.create = function (attr = "") {
        this.attr = attr;
        return this;
    };

    return function () {
        return Object.assign({}, thing);
    };
})(); // end ThingFactory
```

### Create

```js
let thing = ThingFactory().create();
``` 

### Copy

```js
let thing = ThingFactory().create();
let thingCopy = ThingFactory().copy(thing);
``` 