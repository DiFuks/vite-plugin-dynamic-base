# vite-plugin-dynamic-base

<!-- [![NPM version](https://img.shields.io/npm/v/vite-plugin-dynamic-base?color=a1b858&label=)](https://www.npmjs.com/package/vite-plugin-dynamic-base) -->

  <a href="https://www.npmjs.com/package/vite-plugin-dynamic-base">
    <img src="https://img.shields.io/npm/v/vite-plugin-dynamic-base" alt="Version" />
  </a>
  <a href="https://www.npmjs.com/package/vite-plugin-dynamic-base">
    <img src="https://img.shields.io/github/languages/top/chenxch/vite-plugin-dynamic-base" alt="Languages" />
  </a>
  <a href="https://www.npmjs.com/package/vite-plugin-dynamic-base">
    <img src="https://img.shields.io/npm/l/vite-plugin-dynamic-base" alt="License" />
  </a>
  <a href="https://github.com/AttoJS/vite-plugin-dynamic-base/stargazers">
    <img src="https://img.shields.io/github/stars/chenxch/vite-plugin-dynamic-base" alt="Star" />
  </a>
  <a href="https://www.npmjs.com/package/vite-plugin-dynamic-base">
    <img src="https://img.shields.io/npm/dm/vite-plugin-dynamic-base" alt="Download" />
  </a>
  
<p align='center'>
<b>English</b> | <a href="https://github.com/chenxch/vite-plugin-dynamic-base/blob/main/README.zh-CN.md">简体中文</a>
</p>

- 🦾 Resolve all resource files dynamic publicPath, like Webpack's `__webpack_public_path__`.


## Installation

```bash
npm i vite-plugin-dynamic-base -D
```


## Changelog

### 1.0.0

_2023-06-07_

#### Feat

- Using SWC for token transformation （[#23](https://github.com/chenxch/vite-plugin-dynamic-base/pull/23) by [@joarfish](https://github.com/joarfish)）


[Changelogs](./CHANGELOG.md)


## Build Mode

- [x] es
- [x] system

## Compatible plugins

- [x] [@vitejs/plugin-legacy](https://www.npmjs.com/package/@vitejs/plugin-legacy)
- [x] [vite-plugin-pwa](https://www.npmjs.com/package/vite-plugin-pwa)

## Usage

```ts
// vite.config.ts
import { dynamicBase } from 'vite-plugin-dynamic-base'

export default defineConfig({
  // base: "/",
  base: process.env.NODE_ENV === "production" ? "/__dynamic_base__/" : "/",
  plugins: [
    dynamicBase({ /* options */ }),
  ],
})
```

## Configuration

The following show the default values of the configuration

```ts
dynamicBase({
  // dynamic public path var string, default window.__dynamic_base__
  publicPath: 'window.__dynamic_base__',
  // dynamic load resources on index.html, default false. maybe change default true
  transformIndexHtml:  false
})
```

