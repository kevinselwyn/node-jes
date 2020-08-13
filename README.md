# JES

Javascript implementation of the [Advanced Encryption Standard](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard) (AES-128-CBC)

See the parent project [here](https://github.com/kevinselwyn/JES).

## Usage

Install the module via NPM:

```bash
npm install node-jes
```

Require the module in your script:

```js
var jes = require("node-jes");
```

### Encryption

```js
JES.encrypt({
    plaintext: "Attack at dawn!!",
    key: "6162636465666768696a6b6c6d6e6f70",
    iv: "7172737475767778797a7b7c7d7e7f80"
}, output_type);
```

`plaintext`: (When encrypting) The plaintext to encode<br />
`key`: A 16-byte hexadecimal string<br />
`iv`: The initialization vector<br />
`output_type`: Choice of output type

* "hex/array": An array of single-byte hexadecimal strings
* "hex/string": A continuous, 16-byte string
* "ascii/array": An array of single-character strings
* "ascii/string": A continuous string
* "int/array": An array of single-byte integers

### Decryption

```js
JES.decrypt({
    ciphertext: String.fromCharCode(0xd7, 0x9f, 0x73, 0xc1, 0x46, 0x19, 0xe3, 0x78, 0xb0, 0x2a, 0xea, 0xe3, 0x5d, 0x8f, 0xf4, 0x3f, 0x5e, 0xae, 0x3d, 0x97, 0xf3, 0xe6, 0x38, 0x40, 0xed, 0x20, 0x69, 0xde, 0xad, 0xa0, 0xb2, 0x21),
    key: "6162636465666768696a6b6c6d6e6f70",
    iv: "7172737475767778797a7b7c7d7e7f80"
}, output_type);
```

The variables are the same as encryption, except that the input is `ciphertext` now.
