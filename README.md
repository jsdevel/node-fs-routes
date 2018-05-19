# Note This repository has moved to https://github.com/kogosoftwarellc/open-api/tree/master/packages/fs-routes

# fs-routes [![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Coveralls Status][coveralls-image]][coveralls-url]
> Scan a filesystem for route files.

`fs-routes` is the basis for convention based routing tools in node.  You can use
the output of `fs-routes` to load route modules for any web framework.

## Highlights

* Generates routes based on directory structure.
* Caches the results for speed and consistency.
* Framework agnostic.

## Example

This directory strucutre

```
routes/
      `home.js
      |
      `users/
            `:id.js
            `index.js
```

when passed to `fs-routes`

```javascript
var fsRoutes = require('fs-routes');

var output = fsRoutes('routes');
```

returns the following:

```javascript
var output = [
  {
    path: '/my/project/path/routes/home.js',
    route: '/home'
  },
  {
    path: '/my/project/path/routes/users/:id.js',
    route: '/users/:id'
  },
  {
    path: '/my/project/path/routes/users/index.js',
    route: '/users/'
  }
];
```

## LICENSE
``````
The MIT License (MIT)

Copyright (c) 2015 Joseph Spencer

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
``````

[downloads-image]: http://img.shields.io/npm/dm/fs-routes.svg
[npm-url]: https://npmjs.org/package/fs-routes
[npm-image]: http://img.shields.io/npm/v/fs-routes.svg

[travis-url]: https://travis-ci.org/jsdevel/node-fs-routes
[travis-image]: http://img.shields.io/travis/jsdevel/node-fs-routes.svg

[coveralls-url]: https://coveralls.io/r/jsdevel/node-fs-routes
[coveralls-image]: http://img.shields.io/coveralls/jsdevel/node-fs-routes/master.svg
