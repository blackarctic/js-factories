# JS Factories 

A reference for creating factories that create objects in JavaScript.

I have found this to work quite well for most applications.


### Define

```js
let ThingFactory;

ThingFactory = (function () {
    let factory = {};

    return function () {
        let thing = {};

        thing.copy = function (otherThing) {
            thing.attr = otherThing.attr;
            return thing;
        };

        thing.create = function (attr) {
        	thing.attr = attr || "";
        	return thing;
        };

        return thing;
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