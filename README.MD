# L04 Transpiler Swc

> Using swc to transpile and polyfill

swc is a new competitor to Babel. It is written in Rust and up to 20 times faster. This can be very important if you find yourself waiting a long time to build your project.

As a Javascript Developer, I want to target the latest ES features while maintaining browser compatibility, so that I can code fast but support older browsers

This code is based off this article [Why you don’t need Babel](https://blog.logrocket.com/why-you-dont-need-babel/)

## Before and After

Before and after for L04 Transpiler Swc in HTML

<table>
<tr>
  <th>Before</th>
  <th>After</th>
</tr>
<tr>
  <td>
  
  ![Before](shot-before.png 'Before screenshot')
  
  </td>
  <td>
  
  ![After](shot-after.png 'After screenshot')
  
  </td>
</tr>
</table>

## Development

Run `node dist/test.js` from command line

```bash
# cd [YouCustomDevFolder]
git clone git@github.com:klueless-html-samples/L04TranspilerSwc.git && cd L04TranspilerSwc

npm install

# Run the transpiler
npx swc src -d dist

# Run the code
node dist/test.js

# NOTE: There should be no assertion errors, but it will say fetch is not defined since Node.js has no fetch() method. 
```

## Code Setup

```bash
# Setup Transpilers for ES6 support using SWC
npm install --save-dev @swc/cli @swc/core browserslist
```

Add the following to package.json.

```javascript
  "browserslist": [
    "defaults"
  ]
```

Add the following to .swcrc

```json
{
  "env": {
    "coreJs": 3
  },
  "jsc": {
    "parser": {
      "syntax": "ecmascript"
    }
  }
}
```

## License

The code is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Copyright

Copyright (c) David Cruwys. See [MIT License](LICENSE.txt) for further details.
