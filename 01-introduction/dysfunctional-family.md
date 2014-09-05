# Meet the dysfunctional family

- Cookies
- Local Storage / Session Storage
- WebSQL
- IndexedDB
- Browser Cache
- Application Cache
- Service Worker

### Cookies

- Basically work on *every* browser
- Only supports very small pieces of information
- Only supports strings
- Sent on every http request
- Quite fiddly to use without a helper library/function

### Local Storage

- Works on a lot of browsers
- Supports more data than cookies
- Very *fast*
- Only supports strings
- Not sent on http request (only available client side)
- Synchronous, which can cause performance issues

### Local database (WebSQL, IndexedDB)

- One or the other (or both) work on most modern browsers
- Supports more data than local storage (typically around ~50mb, but can be much bigger on Desktop)
- Supports complex data structures and multiple data types
- Built in mechanism for migrations
- Slower than Local Storage
- Not sent on http request (only available client side)
- Asynchronous

### Browser Cache

- Works on every browser
- *Sometimes* does work offline (which can be confusing when trying to test AppCache issues) but...
- It can't be relied on

### Application Cache

- Works on most (90%+) modern browsers
- Best suited for storing application *code*
- The only option to reliably load a website from nothing offline
- Can storage a significant amount of data (50mb+)
- Very difficult use without causing unintended consequences for most websites

### Service Worker

- Application Cache's replacement, but unlikely to be possible to polyfill
- Not available in any browser (bits of it work on some cutting-edge browsers with feature flags switched on)
- Safari / Microsoft have not announced any intention to implement it
- Will only work on https
- Promises to be less difficult to use and cause fewer side effects than Application Cache

Note. There was another storage technology relevant to offline websites called the HTML5 FileSystem API but as of April 2014, [that spec is dead](http://www.html5rocks.com/en/tutorials/file/filesystem/)

#### Q. Which technology do you need to make an offline-first web application?

A. Most, if not all, of them.

---

[← Back to *how*](./how.md) | [Continue to *a promising start* →](../02-a-promising-start)
