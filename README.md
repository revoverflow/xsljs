# xsl.js

XS-Leaks, or Cross-Site Leaks, are a type of security vulnerability that can occur when sensitive data is inadvertently leaked from one website to another. This library provides a comprehensive set of functions and tools to assist researchers in identifying, testing, and exploiting XS-Leaks vulnerabilities.

More informations about XS-Leaks can be found in the [XS-Leaks Wiki](https://xsleaks.dev/).

## Roadmap

- [x] Error probing (using `onerror` and `onload` events and `script` tags)
- [x] Network Timing (using `performance.now()`)
    - [x] Fetch method (using `fetch` API)
    - [x] Image method (using `img` tag)
- [ ] Cache Probing
- [ ] Frame Counting

## Installation

Just include the `xsl.js` file in your HTML page.

## Usage

### Error probing

```javascript
// Using callback
XSL.errorProbe({
    url: "https://example.com",
    timeout: 1000,
    timeoutShouldReturn: true,
    callback: function (result) {
        console.log(result);
    }
});

// Using promise
XSL.errorProbe({
    url: "https://example.com",
    timeout: 1000,
    timeoutShouldReturn: true
}).then(function (result) {
    console.log(result);
});
```

More informations about this can be found in the [XS-Leaks Wiki](https://xsleaks.dev/docs/attacks/error-events/).

### Network Timing

```javascript
// Fetch method
// With this method, the request is made using the Fetch API, which is not supported by all browsers.
// You can with this method specify more options (check out the "xsl.js" file).

// Fetch requests (using callback)

XSL.fetchTimed({
    url: "https://example.com"
    callback: function (result) {
        console.log(result);
    }
});

// Fetch requests (using promise)

XSL.networkTiming({
    url: "https://example.com"
}).then(function (result) {
    console.log(result);
});

// Image method
// With this method, the request is made using an image tag, which is supported by all browsers and is the most reliable method.

// Image tags (using callback)

XSL.imageTimed({
    url: "https://example.com",
    callback: function (result) {
        console.log(result);
    }
});

// Image tags (using promise)

XSL.imageTimed({
    url: "https://example.com"
}).then(function (result) {
    console.log(result);
});
```

More informations about this can be found in the [XS-Leaks Wiki](https://xsleaks.dev/docs/attacks/timing-attacks/network-timing/).