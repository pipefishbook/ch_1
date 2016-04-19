# Overview

Bundling JavaScript is needed to transport Node.js modules from server to browser. 
This chapter shows some examples on how to bundle JavaScript for usage in a web browser.

The importance of learning to bundle JavaScript can be seen from looking at modules at the npm repository. In modules from npmjs, you will often see a statement similar to:

    module.exports = someFunction;

This means `someFunction` can be called from other places in a program. After reading this chapter, you should get a feeling for re-using code from npmjs.org.

As a practical example, and as foundation for other chapters, you will see different approaches to load the Backbone.js library as module.

## npm and browserify

You can load Backbone as module from npm and package it for the browser with browserify. You can check that everything works correctly, with a static file server: 

    $ npm install super-static
    $ ss .
    Server started on port 3474
    127.0.0.1 - - [Tue, 19 Apr 2016 10:17:32 GMT] "GET / HTTP/1.1" 200 253 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.112 Safari/537.36"
    127.0.0.1 - - [Tue, 19 Apr 2016 10:17:32 GMT] "GET /static/bundle.js HTTP/1.1" 200 - "http://localhost:3474/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.112 Safari/537.36"
    127.0.0.1 - - [Tue, 19 Apr 2016 10:17:34 GMT] "GET / HTTP/1.1" 304 - "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_4) AppleWebKit/5

