# Add Code Block

This is a small script to inject code blocks into Markdown files.
This is useful when you want to be able to lint or test code
that appears in READMEs or other documentation.

## Installation

`npm install -g add-code-block`

## Use

With this in the markdown of a file called README.md:

```

<!-- start code block file="./example.js" -->

This gets replaced with the contents of `./example.js`

<!-- end code block -->

```

running:

```sh
cp README.md README.bak
add-code-block README.bak >README.md
```

produces:

    <!-- start code block file="./example.js" -->
    ```js
    'use strict'

    module.exports = {
      sync: (value) => value,
      async: (value, cb) => setTimeout(() => cb(null, value), 0),
      promise: (value) => Promise.resolve(value)
    }
    ```
    <!-- end code block -->
