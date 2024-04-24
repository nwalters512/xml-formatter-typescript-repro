# xml-formatter-typescript-repro

This repository reproduces an issue with the `xml-formatter` package when used in a TypeScript project with `"type": "module"`.

## Steps to reproduce

- Clone this repository
- Install dependencies with `yarn`
- Run `yarn start-esm`; observe that the XML file is formatted correctly
- Run `yarn start-cjs`; observe that the XML file is formatted correctly
- Run `yarn typecheck`; observe that TypeScript complains that `formatXml` is not callable:

```
src/index-esm.ts:3:13 - error TS2349: This expression is not callable.
  Type 'typeof import("/Users/nathan/git/xml-formatter-typescript-repro/node_modules/xml-formatter/dist/types/index")' has no call signatures.

3 console.log(formatXml('<foo><bar/></foo>'));
              ~~~~~~~~~


Found 1 error in src/index-esm.ts:3
```
