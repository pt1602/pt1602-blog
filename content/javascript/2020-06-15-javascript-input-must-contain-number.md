---
title: 'Input must contain number'
author: pt1602
type: post
date: 2020-06-15T19:35:39+00:00
url: /javascript-input-must-contain-number/
---

```javascript
function validateStreet(e) {
    const streetNotice = document.getElementById('streetnotice');
    let currentvalue = e.value;
    let outputvalue = currentvalue.search(/\d/g);

    if (outputvalue === -1) {
        streetNotice.style.display = "block";
    } else {
        streetNotice.style.display = "none";
    }
}
```

[Codepen](https://codepen.io/PT1602/pen/MWKjYqY)