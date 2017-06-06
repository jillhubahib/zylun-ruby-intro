# zylun-ruby-intro
Zylun's Developer Meetup Introduction to Ruby

This presentation uses `slideshow` gem with `reveal.js` template.

## Setup

```
$ gem install slideshow
$ slideshow install reveal.js
```

There is an issue with current `liquid` gem with `slideshow` as reported [here](https://groups.google.com/forum/#!topic/wwwmake/VxxCi1i-_ow), so make sure to install version **`3.0.6`** of `liquid` to get pass this.

## Build

`
$ slideshow build index.md -t reveal.js --h2
`

Open `index.html` in the browser.