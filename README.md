[1]: https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks
[2]: https://lefthook.dev
[3]: https://lefthook.dev/configuration/glob/
[4]: https://eslint.org/

## How was it made?

This is a [Node.js](https://nodejs.org/en) project created with `npm init`.

## Why was it made?

The objective of this repository is to learn and practice [Git Hooks][1] and [Lefthook][2].

## Getting Started

### Install the dependencies

```bash
npm install
```

### See the result

To see the **pre-commit** hook in action, you can modify `index.js` file _forcing an error_, like in the example bellow:

```javascript
import { appendFile } from "node:fs";

const even_numbers = [2, 4, 6, 8];
const odd_numbers = [1, 3, 5, 7, 9, 11];

if (even_numberslength > odd_numbers.length) {
  console.log("There are more even numbers than odd ones.");
} else {
  consolelog("There are more odd numbers then even ones.");
}
```

After that, **stage the changes** and try to **commit** with this command:

```bash
git commit -m 'refactor: force an error on `index.js` file'
```

### How does it work?

The project uses [Lefthook][2] to manage [Git Hooks][1].

The [ESLint][4] package is used in the **pre-commit** hook to catch errors.

The _job_ itself looks for errors on **javascript** files that were **staged**.

The `glob_matcher: doublestar` option was used because the default one deals with `**` at _globs_ in a different way.

You can read more about it [here][3].
