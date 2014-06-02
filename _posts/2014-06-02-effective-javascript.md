---
layout: post
title: Effective Javascript, Know which Javascript you're using
---

ES5 introduced _strict mode_. Enabling this feature allows you to opt in to a restricted version of Javascript that disallows some of the more problematic or error-prone features of the full language.
Strict mode is enabled by addin a special string constant at the beginning of the program:
```
  "use strict";
```
Enable strict mode in a function by placing the directive at the beginning of the function body:
```
  function f(x) {
    "use strict";
  }
```
The syntax of "use strict" means it will be safely ignored by older engines.
"use strict" must be at the top of the file so watch out for file concatenation. All or nothing is best.

The simplest way to structure code for maximum compatibility is to write for strict mode but explicitly wrap the contents in functions that enable strict mode locally.
