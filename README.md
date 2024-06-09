![image](https://github.com/tabaneproject/ecmagen/assets/157493292/666aa4ca-37ae-4f9d-9336-bba18b8e1c6b)
![BasedPkg](https://img.shields.io/badge/escodegen-121216?style=flat-square&labelColor=121216&logo=npm&logoColor=a0a0a0&color=c0c0c0&label=forked%20from) ![CommitActivity](https://img.shields.io/github/commit-activity/w/tabaneproject/ecmagen?style=flat-square&labelColor=121216&logo=github&logoColor=a0a0a0&color=c0c0c0) ![GitHub last commit](https://img.shields.io/github/last-commit/tabaneproject/ecmagen?style=flat-square&labelColor=121216&logo=github&logoColor=a0a0a0&color=c0c0c0)<br>
ECMAGen is an [ECMAScript](http://www.ecma-international.org/publications/standards/Ecma-262.htm) (pka. [JavaScript](http://en.wikipedia.org/wiki/JavaScript)) AST Code Transformator/Generator. Mostly supporting [Mozilla's Parser API](https://developer.mozilla.org/en/SpiderMonkey/Parser_API) AST Specification. This project is a reduxed version of the commonly used [escodegen](https://github.com/estools/escodegen) package. Compared to the original package, this package should be used in a [Node.js](https://en.wikipedia.org/wiki/Node.js) platform.
## How to install
You can either clone the repos from releases, or you can add this current tree as a submodule for a potentially unstable release. To add as a submodule, use:
```sh
git submodules add https://github.com/tabaneproject/ecmagen
```
To get the latest release from the NPM registry, use:
```sh
npm install @tabaneproject/ecmagen
```
## How to use
```js
// Import ECMAGen and your favorite
// Code Parser; and of course the FS.
import ecmagen from '@tabaneproject/ecmagen';
import acorn from 'acorn';
import fs from 'node:fs';

// Use ECMAGen
let text = fs.readFileSync( __dirname + '/testcode.js', { encoding: 'utf-8' } );
let ast = acorn.parse( text, { ecmaVersion: 2020 } );
let output = ecmagen.generate( ast );

// Write Output
fs.writeFileSync( __dirname + '/testcode.copy.js', output );
```
## Hello World Program
```js
// Import ECMAGen
import ecmagen from '@tabaneproject/ecmagen';

// Use ECMAGen
let ast = {
    type: 'BinaryExpression',
    operator: '-',
    left: { type: 'Literal', value: 100 },
    right: { type: 'Literal', value: 60 }
};
let output = ecmagen.generate( ast );
console.log( output ); // 100 - 60
```
# License
Copyright (C) 2012 [Yusuke Suzuki](https://github.com/Constellation) for the original project [escodegen](https://github.com/estools/escodegen) <br>
Copyright (C) 2024 [TabaneProject](https://github.com/tabaneproject) for the reduxed version, [ECMAGen](https://github.com/tabaneproject/ecmagen) <br>
<br>
Copyright (C) 2024 [Botaro Shinomiya](https://github.com/citrizon), for [TabaneProject](https://github.com/tabaneproject) <br>
Copyright (C) 2024 [OSCILLIX](https://github.com/Oscillix), for [TabaneProject](https://github.com/tabaneproject) <br>
Copyright (C) 2024 [Bluskript](https://github.com/Bluskript), for [TabaneProject](https://github.com/tabaneproject) <br>
<br>
And the copyright of the other contributors.

```
Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

*   Redistributions of source code must retain the above copyright
    notice, this list of conditions and the following disclaimer.
*   Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in the
    documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL <COPYRIGHT HOLDER> BE LIABLE FOR ANY
DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF
THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE. 
```
