---
title: CSS :is() and :where()
author: pt1602
date: 2021-03-16T13:15:07+00:00
---
Pseudoclasses I should use more:

```
/* Selects any paragraph inside a header, main
or footer element that is being hovered */
:is(header, main, footer) p:hover {
color: red;
cursor: pointer;
}

/* The above is equivalent to the following */
header p:hover,
main p:hover,
footer p:hover {
color: red;
cursor: pointer;
}
```

[Source](https://developer.mozilla.org/en-US/docs/Web/CSS/:is)

```
/* Selects any paragraph inside a header, main
   or footer element that is being hovered */
:where(header, main, footer) p:hover {
  color: red;
  cursor: pointer;
}

/* The above is equivalent to the following */
header p:hover,
main p:hover,
footer p:hover {
  color: red;
  cursor: pointer;
}
```

[Source](https://developer.mozilla.org/en-US/docs/Web/CSS/:where)
