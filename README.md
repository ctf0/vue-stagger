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
        tag="div"
        :options="{}">

        // your data
    </transition-stagger>
    ```

    |        prop       |      required      |  type  | default |          description          |
    |-------------------|--------------------|--------|---------|-------------------------------|
    | tag               | :x:                | string | ul      |                               |
    | delay             | :white_check_mark: | number |         | in milliseconds               |
    | beforeEnterStyles | :white_check_mark: | object |         | [css-props][css]              |
    | enterStyles       | :white_check_mark: | object |         | [v-props][velo]               |
    | leaveStyles       | :white_check_mark: | object |         | [v-props][velo]               |
    | options           | :x:                | object | {}      | extra velocity [options][opt] |

    [velo]: http://velocityjs.org/#cssSupport
    [opt]: http://velocityjs.org/
    [css]: https://www.w3schools.com/jsref/dom_obj_style.asp
