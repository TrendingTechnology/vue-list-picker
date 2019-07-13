<p align="center">
  <img width="200px" src="./.github/logo.png"><br>
  Simple Vue List Picker component
</p>

<p align="center">
    <a href="https://circleci.com/gh/guastallaigor/vue-list-picker/tree/master"><img src="https://badgen.net/circleci/github/guastallaigor/vue-list-picker/master" alt="Build"></a>
    <a href="https://codecov.io/gh/guastallaigor/vue-list-picker"><img src="https://codecov.io/gh/guastallaigor/vue-list-picker/branch/master/graph/badge.svg" alt="Code Coverage"></a>
    <a href="https://www.npmjs.com/package/vue-list-picker"><img src="https://img.shields.io/npm/dt/vue-list-picker.svg" alt="Total Downloads"></a>
    <a href="https://github.com/guastallaigor/vue-list-picker/releases"><img src="https://img.shields.io/npm/v/vue-list-picker.svg" alt="Latest Release"></a>
    <a href="http://standardjs.com"><img src="https://img.shields.io/badge/code%20style-standard-brightgreen.svg" alt="Style standard"></a>
</p>

## Demo

[![Edit Checkbox](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/o4o10xynoz)

## How to install

### npm

```bash
$ npm install vue-list-picker --save
```

### yarn

```bash
$ yarn add vue-list-picker
```

## Quick start
### Vue.js

You can import in your `main.js` file

```js
import Vue from 'vue'
import VueListPicker from 'vue-list-picker'

Vue.use(VueListPicker)
```

Or locally in any component

```js
import { VueListPicker } from 'vue-list-picker'

export default {
  components: {
    VueListPicker
  }
}
```

### Nuxt.js

You can import as a Nuxt.js plugin

`~/plugins/vue-list-picker.js`
```js
import Vue from 'vue'
import VueListPicker from 'vue-list-picker'

Vue.use(VueListPicker)
```

and then import it in your `nuxt.config.js` file
```js
plugins: [
    '~/plugins/vue-list-picker.js'
]
```

## Basic usage

```html
<template>
  <vue-list-picker :items="items"/>
</template>

<script>
export default {  
  data() {
    const example1 = {
      title: 'Title example 1',
      content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ex dolor, malesuada luctus scelerisque ac, auctor vitae risus. Vivamus risus dolor, faucibus a bibendum quis, facilisis eget odio.'
    }
    const example2 = {
      title: 'Title example 2',
      content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ex dolor, malesuada luctus scelerisque ac, auctor vitae risus. Vivamus risus dolor, faucibus a bibendum quis, facilisis eget odio.'
    }
    const example3 = {
      title: 'Title example 3',
      content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ex dolor, malesuada luctus scelerisque ac, auctor vitae risus. Vivamus risus dolor, faucibus a bibendum quis, facilisis eget odio.'
    }
    const items = [example1, example2, example3]

    return { items }
  }
}
</script>
```

## Props

| Property name       | Type    | Default   | Description                                                                                    |
|---------------------|--------:|:---------:|------------------------------------------------------------------------------------------------|
| items               | Array   | null      | Array of objects to be displayed. Must have at least a content property                        |
| item-selected       | Object  | {}        | Object that is set when it is clicked. Note that `clickable` prop must be set to true          |
| item-unique-key     | String  | ''        | Key to set a blue border to the card when it is clicked (`clickable` prop must be set to true) |
| title-attr          | String  | 'title'   | Name of the property inside the objects, that are in the items array, to set the cards title   |
| title-centered      | Boolean | false     | Centralizes the cards title                                                                    |
| title-class         | String  | ''        | If you want to set a custom class to the cards title, set it here                              |
| title-substr        | String  | 18        | Number of characters to display inside the cards title. Above this, will set a '...' mask      |
| content-attr        | String  | 'content' | Name of the property inside the objects, that are in the items array, to set the cards content |
| content-centered    | Boolean | false     | Centralizes all the cards content text                                                         |
| content-class       | String  | ''        | If you want to set a custom class to the cards content, set it here                            |
| content-substr      | String  | 250       | Number of characters to display inside the cards content. Above this, will set a '...' mask    |
| has-slot            | String  | true      | Set to true if you pass a `<slot>` to override `title` and `content` attributes                |
| min-width           | String  | '200px'   | Min-width of the timeline                                                                      |
| min-height          | String  | ''        | Min-height of the timeline                                                                     |
| timeline-padding    | String  | ''        | Padding of the timeline                                                                        |
| timeline-background | String  | '#E9E9E9' | Background color of the whole timeline                                                         |
| line-color          | String  | '#03A9F4' | Color of the line inside the timeline                                                          |
| clickable           | Boolean | true      | Makes the card clickable that returns the object                                               |

## Instructions

### Generics

1. Right now there's no draggable depency. But if you click and hold your mouse down and drag it into another itens in the same column, all of them it'll selected.
2. The title and content background are both blue (#0052c0), but you can change those using the `content-class` and `title-class` props.
3. By default the height isn't set, but it has an `overflow-y` CSS property, so if you use the height prop, you'll have a vertical scroll inside each panel.
4. If you pass anything other than `top` to `movedItemLocation`, the item after moved will go to the bottom.

### Actions

From top to bottom:

The first button moves all the left items to the right.

The second button moves all the **selected** left items to the right.

The third button moves all the right items to the left.

The fourth button moves all the **selected** right items to the left.

The fifth button unselect all the **selected** items from **all** columns (left and right).

## Development

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/guastallaigor/vue-list-picker/issues)

Fork the project and enter this commands in your terminal

```sh
git clone https://github.com/YOUR_GITHUB_USERNAME/vue-list-picker.git
cd vue-list-picker
yarn
```

### Storybook
For visual testing, this project contains storybook which you can run by doing the next command
```sh
$ yarn storybook:serve
```

### Jest
Before making the PR, if you changed something that needs to be tested, please make the tests inside the `tests/unit` folder.

To run the tests, you can use the next command

```sh
$ yarn test:unit
```

### Commitlint
This project follows the [commitlint](https://github.com/conventional-changelog/commitlint) guidelines, with minor changes.

You can commit using `npm run commit` to help you with that.

There's a `pre-push` hook that runs all the unit tests before you can push it.

If an error occurs, you can use the `npm run commit:retry` command that runs the previous `npm run commit` that you already filled.

<a href="https://www.buymeacoffee.com/guastallaigor" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

## License

MIT © [guastallaigor](https://github.com/guastallaigor/vue-list-picker/blob/master/LICENSE)