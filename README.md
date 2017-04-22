# npmtest-ied

#### basic test coverage for  [ied (v2.3.6)](https://github.com/alexanderGugel/ied#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-ied.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-ied) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-ied.svg)](https://travis-ci.org/npmtest/node-npmtest-ied)

#### An alternative package manager for Node.

[![NPM](https://nodei.co/npm/ied.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/ied)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-ied/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-ied/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-ied/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-ied/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-ied/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-ied/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-ied/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-ied/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-ied/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-ied/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-ied/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-ied/build/test-report.html](https://npmtest.github.io/node-npmtest-ied/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-ied/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-ied/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-ied/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-ied/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-ied/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-ied/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-ied/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-ied/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "ied",
    "version": "2.3.6",
    "bin": {
        "ied": "lib/cmd.js"
    },
    "dependencies": {
        "easy-table": "^1.0.0",
        "force-symlink": "0.0.2",
        "gunzip-maybe": "^1.3.1",
        "init-package-json": "^1.9.4",
        "lodash.frompairs": "^4.0.1",
        "lodash.memoize": "^4.1.0",
        "minimist": "^1.2.0",
        "mkdirp": "^0.5.1",
        "needle": "1.0.0",
        "node-gyp": "^3.4.0",
        "node-pre-gyp": "^0.6.29",
        "node-uuid": "^1.4.7",
        "npm-package-arg": "^4.2.0",
        "ora": "^0.2.3",
        "rimraf": "^2.5.3",
        "rxjs": "5.0.0-rc.1",
        "semver": "^5.2.0",
        "source-map-support": "^0.4.1",
        "tar-fs": "^1.13.0"
    },
    "devDependencies": {
        "babel-cli": "^6.10.1",
        "babel-core": "^6.10.4",
        "babel-eslint": "^6.1.0",
        "babel-plugin-__coverage__": "^11.0.0",
        "babel-plugin-transform-function-bind": "^6.8.0",
        "babel-plugin-transform-object-rest-spread": "^6.8.0",
        "babel-preset-es2015": "^6.9.0",
        "babel-register": "^6.9.0",
        "cross-env": "^2.0.0",
        "esdoc": "^0.4.7",
        "esdoc-es7-plugin": "0.0.3",
        "eslint": "^2.13.1",
        "eslint-config-airbnb-base": "^3.0.1",
        "eslint-plugin-import": "^1.10.2",
        "mocha": "^2.5.3",
        "nyc": "^6.6.1",
        "resolve": "^1.1.7",
        "rimraf": "^2.5.3",
        "sinon": "^1.17.4"
    },
    "scripts": {
        "start": "npm run test:spec -- --watch",
        "test": "npm run test:spec && npm run test:e2e",
        "test:e2e": "rimraf .tmp/test/*; cross-env NODE_ENV=test mocha test/e2e",
        "test:spec": "cross-env NODE_ENV=test mocha test/spec",
        "test:coverage": "nyc --reporter=lcov npm run test:spec -- --reporter dot && nyc report",
        "compile": "rimraf lib/*; cross-env NODE_ENV=production babel src/ -d lib/",
        "compile:watch": "npm run compile -- -w",
        "dev": "rimraf lib/*; cross-env NODE_ENV=development babel src/ -d lib/ -s",
        "dev:watch": "npm run dev -- -w",
        "lint": "eslint src/ test/",
        "prepublish": "npm run compile"
    },
    "repository": {
        "type": "git",
        "url": "git+https://github.com/alexanderGugel/ied.git"
    },
    "author": "Alexander Gugel <alexander.gugel@gmail.com>",
    "license": "MIT",
    "bugs": {
        "url": "https://github.com/alexanderGugel/ied/issues"
    },
    "homepage": "https://github.com/alexanderGugel/ied#readme",
    "description": "An alternative package manager for Node.",
    "files": [
        "lib",
        "USAGE.txt"
    ],
    "nyc": {
        "sourceMap": false,
        "instrument": false
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
