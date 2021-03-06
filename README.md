# keyboardevent-from-electron-accelerator

> Transform an Electron Accelerator string into a DOM KeyboardEvent.

This module export a function that take an Electron Accelerator as input
and return a corresponding KeyboardEvent object.

E.g. `'Ctrl+Alt+C' => {code: 'c', ctrlKey: true, altKey: true}`

---

Patched version of `keyboardevent-from-electron-accelerator` to update virtual key codes at runtime.

---

## Usage

This example convert a string containing an Electron Accelerator to a corresponding KeyboardEvent object. Returned object is the keyevent that would be emitted if that key combination was pressed.

```js
const {toKeyEvent} = require('keyboardevent-from-electron-accelerator');
console.log(toKeyEvent('Shift+Delete'));
```

This will output

    {key: 'Delete', shiftKey: true}

## Context and motivation for this module.

This module is part of an ongoing effort to make [electron-localshortcut](https://github.com/parro-it/electron-localshortcut) less error prone, using keyboard DOM listener instead of 'globalShortcut' method to trigger shortcuts handlers.

`electron-localshortcut` will listen for DOM `keydown` and `keyup` events, and will
trigger shortcuts handlers if emitted DOM events match the Accelerator.

This module wrap the core logic of that match operation.

You can help by testing the module on [runkit](https://npm.runkit.com/keyboardevent-from-electron-accelerator) and [opening an issue](https://github.com/parro-it/keyboardevent-from-electron-accelerator/issues/new) if you found some wrong
result.


## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### toKeyEvent

This function transform an Electron Accelerator string into
a DOM KeyboardEvent object.

**Parameters**

-   `accelerator` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** an Electron Accelerator string, e.g. `Ctrl+C` or `Shift+Space`.

Returns **[object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** a DOM KeyboardEvent object derivate from the `accelerator` argument.

## Install

With [npm](https://npmjs.org/) installed, run

    $ npm install keyboardevent-from-electron-accelerator

## See Also

-   [`noffle/common-readme`](https://github.com/noffle/common-readme)

## License

MIT
