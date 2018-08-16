# Vue Stagger

[![npm](https://img.shields.io/npm/v/vue-stagger.svg?style=for-the-badge)](https://www.npmjs.com/package/vue-stagger) [![npm](https://img.shields.io/npm/dt/vue-stagger.svg?style=for-the-badge)](https://www.npmjs.com/package/vue-stagger)

## Installation

```bash
npm install vue-stagger --save
```

## Usage

- register the component.

    ```js
    window.Vue = require('vue')

    Vue.component('TransitionStagger', require('vue-stagger'))
    ```

- now use it like
    ```vue
    <transition-stagger
        :before-enter-styles="{}"
        :enter-styles="{}"
        :leave-styles="{}"
        :delay="150"
        tag="div">

        // your data
    </transition-stagger>
    ```

    |        prop       |      required      |  type  | default |   description    |
    |-------------------|--------------------|--------|---------|------------------|
    | tag               | :x:                | string | ul      |                  |
    | delay             | :white_check_mark: | number |         |                  |
    | beforeEnterStyles | :white_check_mark: | object |         | [css-props][css] |
    | enterStyles       | :white_check_mark: | object |         | [v-props][velo]  |
    | leaveStyles       | :white_check_mark: | object |         | [v-props][velo]  |

    [velo]: https://github.com/julianshapiro/velocity/wiki/Basic---Properties-Map
    [css]: https://www.w3schools.com/jsref/dom_obj_style.asp

- all the parent component `data & porps` are inharited inside the `transition-stagger`, so your usage remains the same whether you used the `transition-stagger` or not, however for **methods** sadly you'll have to use `$parent.methodName()`
