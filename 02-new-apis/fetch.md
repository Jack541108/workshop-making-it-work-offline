# Fetch

By now I hope I've convinced you that ES6 Promises are the one and only soluton to asynchronous flow and that you will no longer be able to look at a web api built in the Pre-Promise era without feeling a bit like this…

![How I feel about Pre-Promise APIs](http://imgs.xkcd.com/comics/kerning.png)

Let's talk about ajax.

```js
function success(response) { /* do something */ }
var request = new XMLHttpRequest();
request.onreadystatechange = function() {
  if (request.readyState === 4) {
    if (request.status === 200) {
      success(request.response);
    }
  }
};
request.open('https://offline-news-api.herokaupp.com/stories');
request.send();
```

OK, to be fair nobody actually writes this.  They'll normally do something like:-

```js
function success(response) { /* do something */ }
$.get('https://offline-news-api.herokaupp.com/stories', success);
```

Which is much better but what's the point of a standard API that is so difficult to use nobody uses it?

What would be nice if browsers shipped with a simple, _Promise_ based API for _fetching_ ajax requests…

```js
fetch('https://offline-news-api.herokaupp.com/stories')
  .then(success);
```

[Luckily other people think this is a good idea too](http://fetch.spec.whatwg.org/), and is the mechanism you *must* use within Service Worker, which we'll cover later.  Oddly though Chrome hasn't made this available in the front end, however the lovely people at [GitHub](https://www.github.com/github/fetch) have built a polyfill for modern browsers.

---

[← Back to *Promises*](./) | [Continue to *offline todo with IndexedDB* →](../03-offline-todo)
