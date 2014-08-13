# helper-loader [![NPM version](https://badge.fury.io/js/helper-loader.png)](http://badge.fury.io/js/helper-loader)

> Load helpers from file paths, globs or objects, and cache them as normalized objects.

## Install
#### Install with [npm](npmjs.org):

```bash
npm i helper-loader --save-dev
```

## Usage

```js
var Loader = require('helper-loader');
var helpers = new Loader();
```

## API
### [_](index.js#L7)


Module dependencies.


### [loader](index.js#L30)

Create a new instance of `Loader`, optionally passing default `options`.

* `options` **{Object}**: Default options for front-matter and helper naming.

**Example:**

```js
var Loader = require('helper-loader');
var helpers = new Loader();
```


### [.option](index.js#L94)

Set or get an option.

* `key` **{String}**: The name of the option.
* `value` **{*}**: The value to assign.
* returns: {*}

```js
loader.option('a', true)
loader.option('a')
// => true
```


### [.load](index.js#L144)

Resolve and load helpers onto the cache.

* returns **{Object}** `loader`

```js
// require a helper
loader.load(require('foo'));

// Pass a string or array of file paths or glob patterns
loader.load('a.js');
loader.load(['a.js', 'b.js', 'c.js']);
loader.load(['*.js']);

// pass an object
loader.load({
	a: function (str) {
  	return str;
  }
});

// pass an array of objects
helper.load([{
  a: function (str) {
  	return str;
  },
  b: function (str) {
  	return str;
  }
}]);
```


### [.set](index.js#L175)

Store a `helper` on the cache by `name`.

* `name` **{String}**: Helper name
* `helper` **{String}**: File path, glob pattern or object.

```js
loader.set('foo', function(str) {
  return str;
})
```


### [.get](index.js#L195)

Get `helper` from the cache.

* `helper` **{String}**: The name of the helper to get.

```js
loader.get('foo')
//=> [function]
```


## Author

**Jon Schlinkert**

+ [github/assemble](https://github.com/assemble)
+ [twitter/assemble](http://twitter.com/assemble)

## License
Copyright (c) 2014 Jon Schlinkert, contributors.
Released under the MIT license

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on August 13, 2014._