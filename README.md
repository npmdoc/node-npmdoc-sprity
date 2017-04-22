# npmdoc-sprity

#### api documentation for  [sprity (v1.0.8)](https://github.com/sprity/sprity)  [![npm package](https://img.shields.io/npm/v/npmdoc-sprity.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sprity) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sprity.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sprity)

#### A image sprite generator

[![NPM](https://nodei.co/npm/sprity.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/sprity)

- [https://npmdoc.github.io/node-npmdoc-sprity/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-sprity/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sprity/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sprity/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-sprity/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-sprity/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Alexander Slansky",
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
            "name": "aslansky"
        }
    ],
    "name": "sprity",
    "optionalDependencies": {
        "sprity-css": "^1.0.2",
        "sprity-lwip": "^1.0.3"
    },
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
    "version": "1.0.8",
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
