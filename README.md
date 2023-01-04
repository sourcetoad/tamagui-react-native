# Tamagui React Native
_A starter kit isolated specifically for React Native for [Tamagui](https://tamagui.dev)._

If you use Expo - DO NOT use this. You are welcome to just use `tamagui`.

--- 
## Install
```bash
yarn add @sourcetoad/tamagui-react-native
```

* Create/edit the `assets` region of `react-native.config.js`

```js
module.exports = {
  project: {
    ios: {},
    android: {},
  },
  assets: [
    './node_modules/@tamagui/font-inter/otf'
  ],
};
```
* Run `npx react-native-asset`

* Add this line to top of `babel.config.js`

```js
process.env.TAMAGUI_TARGET = 'native'
```

* Add to `babel.config.js`

```js
[
    '@tamagui/babel-plugin',
    {
        components: ['@sourcetoad/tamagui-react-native'],
        config: './tamagui.config.js',
        logTimings: true,
        disableExtraction: process.env.NODE_ENV === 'development'
    }
],
[
    'transform-inline-environment-variables',
    {
        include: 'TAMAGUI_TARGET'
    }
]
```
