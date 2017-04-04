# api documentation for  [sprity (v1.0.8)](https://github.com/sprity/sprity)  [![npm package](https://img.shields.io/npm/v/npmdoc-sprity.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sprity) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sprity.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sprity)
#### A image sprite generator

[![NPM](https://nodei.co/npm/sprity.png?downloads=true)](https://www.npmjs.com/package/sprity)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sprity/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-sprity_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sprity/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-sprity/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-sprity/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Alexander Slansky",
        "email": "alexander@slansky.net",
        "url": "http://slansky.net"
    },
    "bugs": {
        "url": "https://github.com/sprity/sprity/issues"
    },
    "dependencies": {
        "bluebird": "^2.9.24",
        "color": "^0.8.0",
        "colors": "^1.0.3",
        "cssesc": "^0.1.0",
        "fs-extra": "^0.18.2",
        "handlebars": "^3.0.2",
        "imageinfo": "^1.0.4",
        "layout": "~2.2.0",
        "lodash": "^3.7.0",
        "nomnom": "^1.8.1",
        "parse-filepath": "^0.5.0",
        "prettydiff": "^1.11.13",
        "sprity-css": "^1.0.2",
        "sprity-lwip": "^1.0.3",
        "ternary-stream": "^1.2.3",
        "through2": "^0.6.5",
        "vinyl": "^0.4.6",
        "vinyl-fs": "^1.0.0"
    },
    "description": "A image sprite generator",
    "devDependencies": {
        "chai": "^2.2.0",
        "coveralls": "^2.11.2",
        "istanbul": "^0.3.13",
        "mocha": "^2.2.4",
        "mocha-lcov-reporter": "^0.0.2",
        "object-stream": "^0.0.1",
        "through2-spy": "^1.2.0"
    },
    "directories": {},
    "dist": {
        "shasum": "b1afdc61f0cec06c069597ab5dddd8f59d8bbd0c",
        "tarball": "https://registry.npmjs.org/sprity/-/sprity-1.0.8.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "gitHead": "0a39d863cdb9dea22c9457dd8ec04fe41cc163b7",
    "homepage": "https://github.com/sprity/sprity",
    "keywords": [
        "sprites",
        "sprite",
        "coordinates",
        "css",
        "scss",
        "less",
        "sass",
        "sprity",
        "css-sprite",
        "gulpfriendly"
    ],
    "license": "MIT",
    "licenses": [
        {
            "type": "MIT",
            "url": "https://github.com/sprity/sprity/blob/master/LICENSE-MIT"
        }
    ],
    "main": "./index.js",
    "maintainers": [
        {
            "name": "aslansky",
            "email": "alexander@slansky.net"
        }
    ],
    "name": "sprity",
    "optionalDependencies": {
        "sprity-css": "^1.0.2",
        "sprity-lwip": "^1.0.3"
    },
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/sprity/sprity.git"
    },
    "scripts": {
        "coverage": "istanbul cover _mocha --report html -- -R spec",
        "coveralls": "istanbul cover _mocha --report lcovonly -- -R spec && cat ./coverage/lcov.info | coveralls && rm -rf ./coverage",
        "lint": "eslint .",
        "style": "jscs test/*.js lib/**/*.js index.js",
        "test": "mocha --reporter spec"
    },
    "version": "1.0.8"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module sprity](#apidoc.module.sprity)
1.  [function <span class="apidocSignatureSpan">sprity.</span>create (o, cb)](#apidoc.element.sprity.create)
1.  [function <span class="apidocSignatureSpan">sprity.</span>src (o)](#apidoc.element.sprity.src)



# <a name="apidoc.module.sprity"></a>[module sprity](#apidoc.module.sprity)

#### <a name="apidoc.element.sprity.create"></a>[function <span class="apidocSignatureSpan">sprity.</span>create (o, cb)](#apidoc.element.sprity.create)
- description and source-code
```javascript
create = function (o, cb) {
  if (!o.out) {
    throw new Error('output dir missing');
  }

  this.src(o)
    .on('error', handleCallbackError(cb))
    .pipe(vfs.dest(function (file) {
      return file.base;
    }))
    .on('error', handleCallbackError(cb))
    .on('end', function () {
      if (_.isFunction(cb) && !error) {
        cb();
      }
    });
}
```
- example usage
```shell
...

## Usage

### Programatic usage

'''js
var sprity = require('sprity');
sprity.create(options, cb);
'''

### CLI

See [sprity-cli](https://npmjs.org/package/sprity-cli) for how to use 'sprity' on the command line.

### With [Gulp](http://gulpjs.com)
...
```

#### <a name="apidoc.element.sprity.src"></a>[function <span class="apidocSignatureSpan">sprity.</span>src (o)](#apidoc.element.sprity.src)
- description and source-code
```javascript
src = function (o) {
  if (!o.src) {
    throw new Error('src dir missing');
  }

  var opts = _.extend({}, defaults, o);

  var hasStyle = function () {
    return !!opts.style;
  };

  var stream = vfs.src(opts.src)
    .pipe(tile(opts))
    .on('error', handleError())
    .pipe(layout(opts))
    .on('error', handleError())
    .pipe(sprite(opts))
    .on('error', handleError())
    .pipe(ifStream(hasStyle, style(opts)))
    .on('error', handleError())
    .pipe(toVinyl(opts))
    .on('error', handleError())
    .pipe(through2(function (obj, enc, cb) {
      if (obj instanceof Error) {
        cb(obj, null);
      }
      else {
        cb(null, obj);
      }
    }));

  return stream;
}
```
- example usage
```shell
...
   *  creates sprite and style file and save them to disk
   */
  create: function (o, cb) {
if (!o.out) {
  throw new Error('output dir missing');
}

this.src(o)
  .on('error', handleCallbackError(cb))
  .pipe(vfs.dest(function (file) {
    return file.base;
  }))
  .on('error', handleCallbackError(cb))
  .on('end', function () {
    if (_.isFunction(cb) && !error) {
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
