# ease-sential

Truly essential easing object with tween method included

### API

The exported `Easing` object has all common, well known, battle tested, [Robert Penner's Easing Functions](http://robertpenner.com/easing/) plus a `tween` method.

```js

// will log in 1 second from value 0 to value 10 included
Easing.tween({
  from: 0,
  to: 10,
  onProgress: function (value) {
    console.log(value);
  }
});


```

The method returns an object with a `cancel` method to drop the progress event notification at any time.


#### Configuration Object

The object used to configure the tween can have these values:

  * *from*, both number or an object of properties and numbers as value. If this is an object, update will receive a copy with same keys and current values.
  * *to*, both number or an object of properties and numbers as value. If this is an object, update will receive a copy with same keys and current values.
  * *ease*, optional easing function or easing name. The default will be used if omitted.
  * *duration*, optional tween duration in milliseconds. By default it's 1 second.
  * *onprogress*, or *onProgress*, optional callback that will receive per each update the current value.


#### Examples

```js
var willDropIn2 = Easing.tween({
  // passing from/to as objects
  from: {
    x: 10,
    y: 200
  },
  to: {
    x: -35,
    y: 310
  },
  // 5 seconds tween
  duration: 5000,

  // use easeOutCubic method,
  ease: Easing.easeOutCubic,

  // or ease: 'easeOutCubic'

  // logging all updates
  onProgress: function (obj) {
    console.log(obj);
  }
});

// cancel the tween
setTimeout(function () {
  willDropIn2.cancel();
}, 2000);

```



### Easing Functions

These are: easeInQuad, easeOutQuad, easeInOutQuad, easeInCubic, easeOutCubic, easeInOutCubic, easeInQuart, easeOutQuart, easeInOutQuart, easeInQuint, easeOutQuint, easeInOutQuint, easeInSine, easeOutSine, easeInOutSine, easeInExpo, easeOutExpo, easeInOutExpo, easeInCirc, easeOutCirc, easeInOutCirc, easeInElastic, easeOutElastic, easeInOutElastic, easeInBack, easeOutBack, easeInOutBack, easeInBounce, easeOutBounce, easeInOutBounce.

You can see them [illustrated too](http://easings.net)