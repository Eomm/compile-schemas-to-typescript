# Compile Schemas to TypeScript

[![Greenkeeper badge](https://badges.greenkeeper.io/fastify/compile-schemas-to-typescript.svg)](https://greenkeeper.io/)

This module is a wrapper around the `json-schema-to-typescript` library that enables transformation of directories of schemas instead of individual schemas. If directory support is added to the `json-schema-to-typescript` library this module will be archived.

## API

`compileSchema(input: string, output: string): Promise<void>`

The method iterates over the contents of the `input` directory and compiles any `.json` files into TypeScript interfaces and stores the generated output into the specified `output` directory.

```javascript
const compileSchemas = require('compile-schemas-to-typescript')

(async () => {
  try {
    await compileSchemas('./schemas', './types')
  } catch (err) {
    console.error(err)
    process.exit(1)
  }
})()
```