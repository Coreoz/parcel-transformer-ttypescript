Parcel Transformer Ttypescript
==============================
**Disclaimer: this library is not maintained anymore. If someone wants to take it over, we will be happy to link this repo to the the new repository. We can also hand over the NPM repository.**

A replacement of the standard [Parcel v2 transformer Typescript](https://v2.parceljs.org/languages/typescript/#typescript's-tsc)
to use [ttypescript](https://github.com/cevek/ttypescript).
This enables to use easily [custom TypeScript transformers](https://dev.doctorevidence.com/how-to-write-a-typescript-transform-plugin-fc5308fdd943) inside [Parcel 2](https://v2.parceljs.org/) projects.

Usage
-----
Install the dependency:
- Yarn:`yarn add -D parcel-transformer-ttypescript`
- or NPM: `npm install parcel-transformer-ttypescript --save-dev`

Then inside the `.parcelrc` file, reference the transformer:
```json
{
  "extends": "@parcel/config-default",
  "transformers": {
    "*.{ts,tsx}": ["parcel-transformer-ttypescript"]
  }
}
```

In the `tsconfig.json`, reference your TypeScript transformers:
```json
{
  "compilerOptions": {
    "plugins": [
      {"transform": "./build-scripts/di-transformer-adapter.ts" },
      {"transform": "ts-transformer-classname" }
    ]
  }
}
```
