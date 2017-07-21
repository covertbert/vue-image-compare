# Vue Image Compare

## Requirements
* [Vue.js](http://vuejs.org/) (^2.0.0)

## Installation

```bash
npm i vue-image-compare-plus --save
```

## Usage

```javascript
import Vue from 'vue';
import VueImageCompare from 'vue-image-compare-plus';

Vue.use(VueImageCompare);

new Vue({
  data() {
    return {
      before: '/img/before.jpg',
      after: '/img/after.jpg'
    }
  }
}).$mount('#app');
```

```html
<div id="app">
  <image-compare :before="before" :after="after"/>
</div>
```

If you are **not** using using es6, instead of importing add 

```html
<script src="/path/to/vue-image-compare.js"></script>
```

just before closing body tag. 

## Props

| Name | Type | Description | Required | Default |
| --- | --- | --- | --- | --- |
| `before` | `String` | Path to the image image *before* change | Yes | `undefined` |
| `after` | `String` | Path to the image image *after* change | Yes | `undefined` |
| `full` | `Boolean` | Determines if images are stretched to fill parent element. Can be used with help of CSS `object-fit: cover` to create full page image comparison | No | `false` |
| `padding` | `Object` | Set left and right "padding" in pixels, so handle can **not** reach edge of an image | No | `{ left: 0, right: 0 }` |
| `hideAfter` | `Boolean` | Hide image after and handle | No | `false` |
| `handleStartPosition` | `String` | Determine handle start position | No | `center` |

## Slots

- `icon-left` - element to be placed on the left side of the handle
- `icon-right` - element to be placed on the right side of the handle

Example: 

```html
<image-compare before="/img/before.jpg" after="/img/after.jpg" :padding="{ left: 50, right: 50 }">
  <i class="fa fa-angle-left" aria-hidden="true" slot="icon-left"></i>
  <i class="fa fa-angle-right" aria-hidden="true" slot="icon-right"></i>
</image-compare>
```

## License

[MIT](/LICENSE)