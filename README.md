# vitest-inspect-brk

This repository exists to demonstrate an issue with Vitest, where `debugger` statements in test files are not paused on when using the `--inspect-brk` flag that `vitest` supports.

## Setup

To test this, run the following:

```sh
npx vitest --inspect-brk --threads false run demo
```

And connect a debugger. See the [Node documentation on debugger clients](https://nodejs.org/en/docs/guides/debugging-getting-started/#inspector-clients) for more details on this process.

## Expected

The `debugger` in `demo.test.js` would be paused on in the debugger

## Actual

The `debugger` in `demo.test.js` is totally ignored

## Other Information

Debugging tests _does_ work correctly with tools that automatically launch child Node processes with the debugger attached, such as `ndb` or the VSCode JavaScript debugging terminal.
