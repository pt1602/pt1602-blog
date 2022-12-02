---
title: Add styling to head
author: pt1602
type: post
date: 2021-11-25T12:31:42+00:00
url: /javascript-function-to-add-css-to-head/
categories:
  - javascript
tags:
  - css
  - head
  - javascript
  - js
---
<pre class="wp-block-preformatted">const addStyle = () =&gt; {<br />    const style = <strong><em>document</em></strong>.createElement('style');<br />    <strong><em>document</em></strong>.head.append(style);<br />    return (styleString) =&gt; style.textContent = styleString;<br />})();</pre>