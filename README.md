# WebGL2 Nano Currency Proof of Work Generation

Javascript module to generate the proof of work value for [Nano currency](https://nano.org) transactions with the GPU by using a WebGL2 fragment shader that calculates a Blake2B hash.

See the [demo for a working implementation](https://numtel.github.io/nano-webgl-pow/).

WebGL 2 provides bitwise operators unavailable in WebGL 1. These are required for the Blake2B calculation. As of time of writing, WebGL2 is supported in Chrome and Firefox, on desktop and Android. See the [WebGL2 compatibility table](https://caniuse.com/#feat=webgl2) for more information.

## Implements

`window.NanoWebglPow(hashHex, callback, progressCallback);`

Due to using `window.requestAnimationFrame()` to prevent blocking the main thread during generation, the browser tab must remain open during generation.

* `hashHex` `<String>` Previous Block Hash as Hex String
* `callback` `<Function>` Function Called when work value found. Receives single string argument, work value as hex.
* `progressCallback` `<Function>` Optional. Receives single argument: n, number of frames so far. Return true to abort.

## Acknowledgements

* [jaimehgb/RaiBlocksWebAssemblyPoW](https://github.com/jaimehgb/RaiBlocksWebAssemblyPoW) WASM implementation of proof of work generation
* [dcposch/blakejs](https://github.com/dcposch/blakejs) Javascript blake2b as template

## License

MIT
