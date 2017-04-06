# api documentation for  [gpio (v0.2.7)](https://github.com/EnotionZ/GpiO)  [![npm package](https://img.shields.io/npm/v/npmdoc-gpio.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gpio) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gpio.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gpio)
#### Talk to your Raspberry PI's general purpose inputs and outputs

[![NPM](https://nodei.co/npm/gpio.png?downloads=true)](https://www.npmjs.com/package/gpio)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gpio/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gpio_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gpio/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gpio/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gpio/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Dominick Pham",
        "email": "dominick@dph.am",
        "url": "http://dph.am"
    },
    "bugs": {
        "url": "https://github.com/EnotionZ/GpiO/issues"
    },
    "dependencies": {},
    "description": "Talk to your Raspberry PI's general purpose inputs and outputs",
    "devDependencies": {
        "sinon": "*"
    },
    "directories": {},
    "dist": {
        "shasum": "bf386c88961efd0a4f6a0ff7167ac0ff3997eab9",
        "tarball": "https://registry.npmjs.org/gpio/-/gpio-0.2.7.tgz"
    },
    "gitHead": "a8e3f5c72df067462b25343918af2718712cda17",
    "homepage": "https://github.com/EnotionZ/GpiO",
    "keywords": [
        "gpio",
        "raspberry",
        "pi"
    ],
    "licenses": [
        {
            "type": "MIT",
            "url": "https://raw.github.com/EnotionZ/GpiO/master/LICENSE"
        }
    ],
    "main": "./lib/gpio.js",
    "maintainers": [
        {
            "name": "dph",
            "email": "dominick@dph.am"
        }
    ],
    "name": "gpio",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/EnotionZ/GpiO.git"
    },
    "scripts": {},
    "version": "0.2.7"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gpio](#apidoc.module.gpio)
1.  boolean <span class="apidocSignatureSpan">gpio.</span>logging
1.  [function <span class="apidocSignatureSpan">gpio.</span>export (headerNum, direction)](#apidoc.element.gpio.export)
1.  [function <span class="apidocSignatureSpan">gpio.</span>unexport (number, fn)](#apidoc.element.gpio.unexport)



# <a name="apidoc.module.gpio"></a>[module gpio](#apidoc.module.gpio)

#### <a name="apidoc.element.gpio.export"></a>[function <span class="apidocSignatureSpan">gpio.</span>export (headerNum, direction)](#apidoc.element.gpio.export)
- description and source-code
```javascript
export = function (headerNum, direction) { return new GPIO(headerNum, direction); }
```
- example usage
```shell
...

##### Standard setup

'''js
var gpio = require("gpio");

// Calling export with a pin number will export that header and return a gpio header instance
var gpio4 = gpio.export(4, {
// When you export a pin, the default direction is out. This allows you to set
// the pin value to either LOW or HIGH (3.3V) from your program.
direction: 'out',

// set the time interval (ms) between each read when watching for value changes
// note: this is default to 100, setting value too low will cause high CPU usage
interval: 200,
...
```

#### <a name="apidoc.element.gpio.unexport"></a>[function <span class="apidocSignatureSpan">gpio.</span>unexport (number, fn)](#apidoc.element.gpio.unexport)
- description and source-code
```javascript
unexport = function (number, fn) {
	_write(number, gpiopath + 'unexport', function(err) {
		if(err) return logError(err);
		if(typeof fn === 'function') fn();
	}, 1);
}
```
- example usage
```shell
...
});
gpio4.set(0, function() {
   console.log(gpio4.value);    // should log 0
});
'''
'''js
// unexport program when done
gpio4.unexport();
'''

##### EventEmitter
This library uses node's [EventEmitter](http://nodejs.org/api/events.html) which allows you to watch
for value changes and fire a callback.
'''js
// bind to the "change" event
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
