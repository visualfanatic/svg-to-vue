<h1 align="center">svg-to-vue</h1>
<p align="center">Utility to convert SVG code into Vue component definition</p>

## Instalation

[![Greenkeeper badge](https://badges.greenkeeper.io/visualfanatic/svg-to-vue.svg)](https://greenkeeper.io/)

``` bash
npm i svg-to-vue

yarn add svg-to-vue
```

## Usage
``` js
const svgToVue = require('svg-to-vue');

const code = `
  <svg width="300" height="200" xmlns="http://www.w3.org/2000/svg">
    <rect width="100%" height="100%" fill="red" />
  </svg>
`;

svgToVue(code)
  .then((component) => {
    // `component` contains Vue component definition
    console.log(component);
  });
```

## API
``` js
svgToVue(code, {
  svgoConfig: {
    plugins: [
      {
        prefixIds: true,
      },
    ],
  },
  svgoPath: 'some/path/to.svg',
  esmExport: true,
});
```

| Name | Type | Default value | Description |
| - | - | - | - |
| `svgoConfig` | `Object`/`Boolean` | `{}` | Configuration object passed to SVGO or `false` to disable optimization |
| `svgoPath` | `String` | `null` | Path to SVG file which is used by SVGO `prefixIds` plugin to generate unique IDs |
| `esmExport` | `Boolean` | `false` | Module export format: `true` for EcmaScript or `false` for CommonJS |
