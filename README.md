# xsl.js

XS-Leaks, or Cross-Site Leaks, are a type of security vulnerability that can occur when sensitive data is inadvertently leaked from one website to another. This library provides a comprehensive set of functions and tools to assist researchers in identifying, testing, and exploiting XS-Leaks vulnerabilities.

More informations about XS-Leaks can be found in the [XS-Leaks Wiki](https://xsleaks.dev/).

## Roadmap

- [x] Error probing (using `onerror` and `onload` events and `script` tags)

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