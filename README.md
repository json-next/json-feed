
Comments • Unquoted keys • Multi-line strings • Trailing commas • Optional commas • Auto-Wrapped in Object/Hash • Simple Version • and more

# JSON: 1.1 # JSON with Extensions (JSONX) Feed

_JSON Feed Evolved for Humans - Easy-to-Write, Easy-to-Read_ 


## Welcome

_What's a Feed in JSON with Extension? Why? Why?_

JSON Feed is a feed format similar to RSS and Atom in JSON. Example:

```
{
    "version": "https://jsonfeed.org/version/1",
    "title": "My Example Feed",
    "home_page_url": "https://example.org/",
    "feed_url": "https://example.org/feed.json",
    "items": [
        {
            "id": "2",
            "content_text": "This is a second item.",
            "url": "https://example.org/second-item"
        },
        {
            "id": "1",
            "content_html": "<p>Hello, world!</p>",
            "url": "https://example.org/initial-post"
        }
    ]
}
```

See  [jsonfeed.org](https://jsonfeed.org).


Now thanks to JSON: 1.1 # JSON with Extensions (JSONX) let's 
make JSON Feed easier-to-write and easier-to-read.
How about?

```
 # JSON Feed Simplified w/ JSON v1.1, JSON with Extensions (JSONX)
 
 version       : 1
 title         : 'My Example Feed'
 home_page_url : 'https://example.org/'
 feed_url      : 'https://example.org/feed.json'
 items         : [
   {
     id           : '2'
     content_text : 'This is a second item.'
     url          : 'https://example.org/second-item'
   }
   {
     id           : '1'
     content_html : '<p>Hello, world!</p>'
     url          : 'https://example.org/initial-post'
   }
 ]
 ```
 

## Spec

_JSON v1.1 Feed Format Specification in English_

JSON v1.1 Feed follows JSON feeds but allows allows all JSON v1.1 JSON extensions e.g.:

- quotes for strings are optional if they follow JavaScript identifier rules (with some additions e.g. `.-+/^@`)
- single line comments start with `#` or `//`
- commas after object key-value pairs are optional
- commas after array items are optional
- and much more

Plus some more extra for JSON Feed:

- feed gets auto-wrapped in object, that is, `{ ... }`
- version number gets shortend to `1` instead of `https://jsonfeed.org/version/1`




## Meta

**License**

![](https://publicdomainworks.github.io/buttons/zero88x31.png)

The JSON with Extensions format is dedicated to the public domain. Use it as you please with no restrictions whatsoever.

**Questions? Comments?**

Post them to the [wwwmake forum](http://groups.google.com/group/wwwmake). Thanks!

