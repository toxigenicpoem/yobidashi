yobidashi
=========

A Standalone Micro JavaScript Pub Sub Utility for the _Browser_. Helping you develop modular javascript.

* does not build or manage a messaging/work que
* subs need to be established to listen before pubs are emitted.
* has NO dependencies outside of RequireJS for loading
* supports IE6-10, and Modern (Firefox, Safari, Chrome, Opera).
* uses native eventing

subscribe to an event:
```javascript
//create a call back
var cb = function(){
    console.log('cb event happened');
}

//subscribe to some channel
yobidashi.sub('/channel', cb);
```

publish:
```javascript
//publish to some channel
yobidashi.pub('/channel');
```

unsubscribe:
```javascript
//create a call back
var cb = function(){
    console.log('cb event happened');
}

//subscribe to some channel
yobidashi.sub('/channel', cb);

//unsubscribe with reference to same callback
yobidashi.unsub('/channel', cb);
```

use bind(included with yobidashi) to pass data:
```javascript
//create a data object
var data = {foo: 'bar'};

//create a call back bound to data
var cb = yobidashi.bind(function(){
    console.log(this.foo);
});
```

Use banzuke standalone message que to simplfy moving data around!:
https://github.com/toxigenicpoem/banzuke

Simple Example Page:
http://jsfiddle.net/toxigenicpoem/Tqevs/


The MIT License (MIT)

Copyright (c) 2013 Derek M. Anderson

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