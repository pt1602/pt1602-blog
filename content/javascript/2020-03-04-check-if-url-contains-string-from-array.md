---
title: Check if URL contains string from array
author: pt1602
type: post
date: 2020-03-04T10:06:15+00:00
---

```javascript
let contains = false;

const array = ['imprint', 'data-protection', 'terms-of-use'];

const currentUrl = '/imprint'.toUpperCase();
// replace with window.location.href

array.forEach(function (item) {
    let currentItem = item.toUpperCase();

    if (currentUrl.includes(currentItem)) {
        contains = true;
    }
});

console.log(contains);
```

[CodePen](https://codepen.io/PT1602/pen/QWbKxQg)