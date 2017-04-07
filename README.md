# api documentation for  [paralleljs (v0.2.1)](https://github.com/adambom/parallel.js#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-paralleljs.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-paralleljs) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-paralleljs.svg)](https://travis-ci.org/npmdoc/node-npmdoc-paralleljs)
#### parallel.js enables easy multi-thread processing in javascript

[![NPM](https://nodei.co/npm/paralleljs.png?downloads=true)](https://www.npmjs.com/package/paralleljs)

[![apidoc](https://npmdoc.github.io/node-npmdoc-paralleljs/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-paralleljs_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-paralleljs/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-paralleljs/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-paralleljs/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Adam Savitzky",
        "email": "adam.savitzky@gmail.com"
    },
    "bugs": {
        "url": "https://github.com/adambom/parallel.js/issues"
    },
    "contributors": [
        {
            "name": "Sebastian Mayr",
            "email": "sebmaster16@gmail.com",
            "url": "http://s3bmaster.blogspot.co.at/"
        }
    ],
    "dependencies": {},
    "description": "parallel.js enables easy multi-thread processing in javascript",
    "devDependencies": {
        "jasmine-node": "x",
        "q": "x"
    },
    "directories": {
        "lib": "lib",
        "test": "test"
    },
    "dist": {
        "shasum": "ebca745d3e09c01e2bebcc14858891ff4510e926",
        "tarball": "https://registry.npmjs.org/paralleljs/-/paralleljs-0.2.1.tgz"
    },
    "engines": {
        "node": ">=0.9.10"
    },
    "homepage": "https://github.com/adambom/parallel.js#readme",
    "keywords": [
        "parallel",
        "spawn",
        "map",
        "thread",
        "parallel.js",
        "workers",
        "webworkers"
    ],
    "license": "BSD",
    "main": "lib/parallel.js",
    "maintainers": [
        {
            "name": "asavitzky",
            "email": "adam.savitzky@gmail.com"
        }
    ],
    "name": "paralleljs",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/adambom/parallel.js.git"
    },
    "scripts": {
        "test": "jasmine-node --verbose test/specs"
    },
    "testling": {
        "scripts": [
            "test/lib/jasmine/jasmine.js",
            "test/specs/*.js",
            "test/runner.js"
        ]
    },
    "version": "0.2.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module paralleljs](#apidoc.module.paralleljs)
1.  [function <span class="apidocSignatureSpan">paralleljs.</span>Worker (url)](#apidoc.element.paralleljs.Worker)
1.  [function <span class="apidocSignatureSpan">paralleljs.</span>isSupported ()](#apidoc.element.paralleljs.isSupported)
1.  object <span class="apidocSignatureSpan">paralleljs.</span>Worker.prototype

#### [module paralleljs.Worker](#apidoc.module.paralleljs.Worker)
1.  [function <span class="apidocSignatureSpan">paralleljs.</span>Worker (url)](#apidoc.element.paralleljs.Worker.Worker)

#### [module paralleljs.Worker.prototype](#apidoc.module.paralleljs.Worker.prototype)
1.  [function <span class="apidocSignatureSpan">paralleljs.Worker.prototype.</span>postMessage (obj)](#apidoc.element.paralleljs.Worker.prototype.postMessage)
1.  [function <span class="apidocSignatureSpan">paralleljs.Worker.prototype.</span>terminate ()](#apidoc.element.paralleljs.Worker.prototype.terminate)
1.  object <span class="apidocSignatureSpan">paralleljs.Worker.prototype.</span>onerror
1.  object <span class="apidocSignatureSpan">paralleljs.Worker.prototype.</span>onmessage



# <a name="apidoc.module.paralleljs"></a>[module paralleljs](#apidoc.module.paralleljs)

#### <a name="apidoc.element.paralleljs.Worker"></a>[function <span class="apidocSignatureSpan">paralleljs.</span>Worker (url)](#apidoc.element.paralleljs.Worker)
- description and source-code
```javascript
function Worker(url) {
	var that = this;
	this.process = ps.fork(url);
	this.process.on('message', function (msg) {
		if (that.onmessage) {
			that.onmessage({ data: JSON.parse(msg) });
		}
	});
	this.process.on('error', function (err) {
		if (that.onerror) {
			that.onerror(err);
		}
	});
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.paralleljs.isSupported"></a>[function <span class="apidocSignatureSpan">paralleljs.</span>isSupported ()](#apidoc.element.paralleljs.isSupported)
- description and source-code
```javascript
isSupported = function (){ return _supports; }
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.paralleljs.Worker"></a>[module paralleljs.Worker](#apidoc.module.paralleljs.Worker)

#### <a name="apidoc.element.paralleljs.Worker.Worker"></a>[function <span class="apidocSignatureSpan">paralleljs.</span>Worker (url)](#apidoc.element.paralleljs.Worker.Worker)
- description and source-code
```javascript
function Worker(url) {
	var that = this;
	this.process = ps.fork(url);
	this.process.on('message', function (msg) {
		if (that.onmessage) {
			that.onmessage({ data: JSON.parse(msg) });
		}
	});
	this.process.on('error', function (err) {
		if (that.onerror) {
			that.onerror(err);
		}
	});
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.paralleljs.Worker.prototype"></a>[module paralleljs.Worker.prototype](#apidoc.module.paralleljs.Worker.prototype)

#### <a name="apidoc.element.paralleljs.Worker.prototype.postMessage"></a>[function <span class="apidocSignatureSpan">paralleljs.Worker.prototype.</span>postMessage (obj)](#apidoc.element.paralleljs.Worker.prototype.postMessage)
- description and source-code
```javascript
postMessage = function (obj) {
	this.process.send(JSON.stringify({ data: obj }));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.paralleljs.Worker.prototype.terminate"></a>[function <span class="apidocSignatureSpan">paralleljs.Worker.prototype.</span>terminate ()](#apidoc.element.paralleljs.Worker.prototype.terminate)
- description and source-code
```javascript
terminate = function () {
	this.process.kill();
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
