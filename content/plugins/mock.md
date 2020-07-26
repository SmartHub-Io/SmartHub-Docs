---
description: ''
sidebar: 'plugins'
next: '/plugins/shelly/'
prev: '/plugins/'
---

# Mock

This is a test page for shelly plugins

## Navigation

The standard navigation on the top left is defined in the `gridsome.config.js` file. The configuration is very simple. It just needs a `settings > nav` property which takes a `links` property that defines every link that should be displayed at the top.

```js
module.exports = {
  settings: {
    nav: {
      links: [
        { path: '/docs/', title: 'Docs' }
      ]
    },
  }
}
```
