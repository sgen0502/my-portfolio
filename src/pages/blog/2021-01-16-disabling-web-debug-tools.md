---
templateKey: blog-post
title: Disabling Web Debug Tools
date: 2021-01-16T15:46:31.906Z
description: >-
  Even though you minify or obfuscate your javascript, there is still
  possibility that your application might get exploit by someone.

  It is simply because Chrome or Firefox Debuggers are powerful enough to help attackers to analyze your code.

  I am introducing how to disable it.
featuredpost: true
featuredimage: /img/apple-touch-icon.png
tags:
  - Javascript
  - Secuirty
---
## 1. How to do it?

Simply embed the script part of the code below in your index.html

<!--StartFragment-->

```
<html>
<body>
<p>please open developer tools</p>
<script src="https://sindresorhus.com/devtools-detect/index.js"></script>

<script>
window.addEventListener('devtoolschange', function () {
  while(true) {
    debugger
  }
})
</script>
</body>
</html>
```

<!--EndFragment-->