
Comments • Unquoted keys • Multi-line strings • Trailing commas • Optional commas • Auto-wrapped feed object • Simple feed version string • `<..-..>` shortcuts • Optional `=` is the new `:` • and more


# JSON v1.1 Feed

_JSON Feed Evolved for Humans - Easy-to-Write, Easy-to-Read_ 


## Welcome

_What's a Feed in JSON with Extensions (JSONX) in JSON v1.1? Why? Why?_

JSON Feed is a feed format similar to RSS and Atom in JSON. See [jsonfeed.org »](https://jsonfeed.org). Example:

```
{
    "version":       "https://jsonfeed.org/version/1",
    "title":         "My Example Feed",
    "home_page_url": "https://example.org/",
    "feed_url":      "https://example.org/feed.json",
    "items": [
        {
            "id":           "2",
            "content_text": "This is a second item.",
            "url":          "https://example.org/second-item"
        },
        {
            "id":           "1",
            "content_html": "<p>Hello, world!</p>",
            "url":          "https://example.org/initial-post"
        }
    ]
}
```


Now thanks to [JSON: 1.1 # JSON with Extensions (JSONX)](https://jsonii.github.io) let's 
make JSON Feed easier-to-write and easier-to-read.
How about?


**"Classic" Colon (:) Variant**

Note: You can use unquoted keys  and all commas are optional.

```
 # JSON Feed shortened w/ JSON v1.1, JSON with Extensions (JSONX)
 
 version       : '1'
 title         : 'My Example Feed'
 home_page_url : 'https://example.org/'
 feed_url      : 'https://example.org/feed.json'
 items         : [
 { 
    id           : '2'
    content_text : 'This is a second item.'
    url          : 'https://example.org/second-item'
 } {
    id           : '1'
    content_html : '<p>Hello, world!</p>'
    url          : 'https://example.org/initial-post'
 }]
 ```


**"Classic" Colon (:) Variant with (<..-..>) Shortcuts**

Note: You can shortcut `[{..},{..}]` with `<..-..>`.

```
 # JSON Feed shortened w/ JSON v1.1, JSON with Extensions (JSONX)
 
 version       : '1'
 title         : 'My Example Feed'
 home_page_url : 'https://example.org/'
 feed_url      : 'https://example.org/feed.json'
 items         : 
 <  id           : '2'
    content_text : 'This is a second item.'
    url          : 'https://example.org/second-item'
    -
    id           : '1'
    content_html : '<p>Hello, world!</p>'
    url          : 'https://example.org/initial-post'
 >
 ```
 
**"Alternate" Equals (=) Variant**

Note: Using `=` as key/value separator lets you use unquoted urls or datetimes - because the colon (`:`) is no longer special.

```
 # JSON Feed shortened w/ JSON v1.1, JSON with Extensions (JSONX)
 
 version       = '1'
 title         = 'My Example Feed'
 home_page_url = https://example.org/
 feed_url      = https://example.org/feed.json
 items         = 
 <  id           = '2'
    content_text = 'This is a second item.'
    url          = https://example.org/second-item
    -
    id           = '1'
    content_html = '<p>Hello, world!</p>'
    url          = https://example.org/initial-post
 >
 ```
 
 
 

## Spec

_Feed Format Specification in English_

JSON v1.1 Feed follows JSON Feed but allows all JSON v1.1 extensions e.g.:

- quotes for strings are optional if they follow JavaScript identifier rules (with some additions e.g. `.-+/^@`)
- single line comments start with `#` or `//`
- commas after object key-value pairs are optional
- commas after array items are optional
- `<..>`shortcut for `[{..}]`
- `-` shortcut for `},{` 
- and much more

Plus some extras for JSON Feed:

- feed gets auto-wrapped in object, that is, `{ ... }`
- version number gets shortend to `1` instead of `https://jsonfeed.org/version/1`



## Examples


### Podcast

**"Classic" Colon (:) Variant with (<..-..>) Shortcuts**

``` text
version         : '1'
user_comment    : 'This is a podcast feed. You can add this feed to your podcast client using the following URL: http://therecord.co/feed.json'
title           : 'The Record'
home_page_url   : 'http://therecord.co/'
feed_url        : 'http://therecord.co/feed.json'
items           :    
  < id            : 'http://therecord.co/chris-parrish'
    title         : 'Special #1 - Chris Parrish'
    url           : 'http://therecord.co/chris-parrish'
    content_text  : `Chris has worked at Adobe and as a founder of Rogue Sheep, 
                        which won an Apple Design Award for Postage. Chris's new company is Aged & Distilled 
                        with Guy English - which shipped Napkin, a Mac app for visual collaboration. 
                        Chris is also the co-host of The Record. He lives on Bainbridge Island, 
                        a quick ferry ride from Seattle.`
    content_html  : `Chris has worked at <a href="http://adobe.com/">Adobe</a> and as a founder of Rogue Sheep,
                        which won an Apple Design Award for Postage. Chris's new company is Aged & Distilled
                        with Guy English - which shipped <a href="http://aged-and-distilled.com/napkin/">Napkin</a>, 
                        a Mac app for visual collaboration. Chris is also the co-host of The Record. 
                        He lives on <a href="http://www.ci.bainbridge-isl.wa.us/">Bainbridge Island</a>, 
                        a quick ferry ride from Seattle.`
    summary        : 'Brent interviews Chris Parrish, co-host of The Record and one-half of Aged & Distilled.'
    date_published : '2014-05-09T14:04:00-07:00'
    attachments    : 
    <  url           : 'http://therecord.co/downloads/The-Record-sp1e1-ChrisParrish.m4a'
       mime_type     : audio/x-m4a
       size_in_bytes : 89_970_236
       duration_in_seconds : 6_629
    >
  >
```

**"Alternate" Equals (=) Variant**

``` text
version         = '1'
user_comment    = 'This is a podcast feed. You can add this feed to your podcast client using the following URL: http://therecord.co/feed.json'
title           = 'The Record'
home_page_url   = http://therecord.co/
feed_url        = http://therecord.co/feed.json
items           =    
  < id            = http://therecord.co/chris-parrish
    title         = 'Special #1 - Chris Parrish'
    url           = http://therecord.co/chris-parrish
    content_text  = `Chris has worked at Adobe and as a founder of Rogue Sheep, 
                        which won an Apple Design Award for Postage. Chris's new company is Aged & Distilled 
                        with Guy English - which shipped Napkin, a Mac app for visual collaboration. 
                        Chris is also the co-host of The Record. He lives on Bainbridge Island, 
                        a quick ferry ride from Seattle.`
    content_html  = `Chris has worked at <a href="http://adobe.com/">Adobe</a> and as a founder of Rogue Sheep,
                        which won an Apple Design Award for Postage. Chris's new company is Aged & Distilled
                        with Guy English - which shipped <a href="http://aged-and-distilled.com/napkin/">Napkin</a>, 
                        a Mac app for visual collaboration. Chris is also the co-host of The Record. 
                        He lives on <a href="http://www.ci.bainbridge-isl.wa.us/">Bainbridge Island</a>, 
                        a quick ferry ride from Seattle.`
    summary        = 'Brent interviews Chris Parrish, co-host of The Record and one-half of Aged & Distilled.'
    date_published = 2014-05-09T14:04:00-07:00
    attachments    = 
    <  url           = http://therecord.co/downloads/The-Record-sp1e1-ChrisParrish.m4a
       mime_type     = audio/x-m4a
       size_in_bytes = 89_970_236
       duration_in_seconds = 6_629
    >
  >
```

the same as ye old' "vanilla" JSON:

```
{
    "version": "https://jsonfeed.org/version/1",
    "user_comment": "This is a podcast feed. You can add this feed to your podcast client using the following URL: http://therecord.co/feed.json",
    "title": "The Record",
    "home_page_url": "http://therecord.co/",
    "feed_url": "http://therecord.co/feed.json",
    "items": [
        {
            "id": "http://therecord.co/chris-parrish",
            "title": "Special #1 - Chris Parrish",
            "url": "http://therecord.co/chris-parrish",
            "content_text": "Chris has worked at Adobe and as a founder of Rogue Sheep, which won an Apple Design Award for Postage. Chris's new company is Aged & Distilled with Guy English - which shipped Napkin, a Mac app for visual collaboration. Chris is also the co-host of The Record. He lives on Bainbridge Island, a quick ferry ride from Seattle.",
            "content_html": "Chris has worked at <a href=\"http://adobe.com/\">Adobe</a> and as a founder of Rogue Sheep, which won an Apple Design Award for Postage. Chris's new company is Aged & Distilled with Guy English - which shipped <a href=\"http://aged-and-distilled.com/napkin/\">Napkin</a>, a Mac app for visual collaboration. Chris is also the co-host of The Record. He lives on <a href=\"http://www.ci.bainbridge-isl.wa.us/\">Bainbridge Island</a>, a quick ferry ride from Seattle.",
            "summary": "Brent interviews Chris Parrish, co-host of The Record and one-half of Aged & Distilled.",
            "date_published": "2014-05-09T14:04:00-07:00",
            "attachments": [
                {
                    "url": "http://therecord.co/downloads/The-Record-sp1e1-ChrisParrish.m4a",
                    "mime_type": "audio/x-m4a",
                    "size_in_bytes": 89970236,
                    "duration_in_seconds": 6629
                }
            ]
        }
    ]
}
```


## More Feed Formats

- [**Feed.TXT**](https://feedtxt.github.io) - free feeds format in plain text w/ structured meta data
- [**Feed.HTML**](https://feedhtml.github.io) -  free feeds format in hypertext markup language (html) w/ structured meta data
- For more formats see the [Formats @ Awesome Feeds](https://github.com/feedparser/awesome-feeds#formats) collection.



## Meta

**License**

![](https://publicdomainworks.github.io/buttons/zero88x31.png)

The JSON v1.1 Feed format is dedicated to the public domain. Use it as you please with no restrictions whatsoever.

**Questions? Comments?**

Post them to the [wwwmake forum](http://groups.google.com/group/wwwmake). Thanks!

