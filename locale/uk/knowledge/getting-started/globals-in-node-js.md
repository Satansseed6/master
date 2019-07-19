---
title: The built-in globals in Node.js
date: '2011-08-26T10:08:50.000Z'
tags:
  - core
  - globals
difficulty: 1
layout: knowledge-post.hbs
---

Node.js has a number of built-in global identifiers that every Node.js developer should have some familiarity with.  Some of these are true globals, being visible everywhere; others exist at the module level, but are inherent to every module, thus being pseudo-globals.

First, let's go through the list of 'true globals':

- `global` - The global namespace.  Setting a property to this namespace makes it globally visible within the running process.
- `process` - Node's built-in `process` module, which provides interaction with the current Node process.  [Read More](/uk/knowledge/getting-started/the-process-module)
- `console` - Node's built-in `console` module, which wraps various STDIO functionality in a browser-like way.  [Read More](/uk/knowledge/getting-started/the-console-module)
- `setTimeout()`, `clearTimeout()`, `setInterval()`, `clearInterval()` - The built-in timer functions are globals. [Read More](/uk/knowledge/javascript-conventions/what-are-the-built-in-timer-functions)

As mentioned above, there are also a number of 'pseudo-globals' included at the module level in every module:

- `module`, `module.exports`, `exports` - These objects all pertain to Node's module system.  [Read More](/uk/knowledge/getting-started/what-is-require)
- __filename - The `__filename` keyword contains the path of the currently executing file.  Note that this is not defined while running the [Node REPL](/uk/knowledge/REPL/how-to-use-nodejs-repl).
- __dirname - Like `__filename`, the `__dirname` keyword contains the path to the root directory of the currently executing script.  Also not present in the Node REPL.
- require() - The `require()` function is a built-in function, exposed per-module, that allows other valid modules to be included.  [Read More](/uk/knowledge/getting-started/what-is-require)

Much of this functionality can be extremely useful for a Node.js developer's daily life - but at the very least, remember these as bad names to use for your own functions! 
