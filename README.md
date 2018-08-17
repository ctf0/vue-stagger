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
        :before-enter-styles="{translateY: -30, opacity: 0}"
        :enter-styles="{translateY: 0, opacity: 1}"
        :leave-styles="{translateY: 30, opacity: 0}"
        :delay="150"
        tag="div"
        :options="{}"
        :enter-at-once="false"
        :leave-at-once="true">

        // your data
    </transition-stagger>
    ```

    |        prop       |      required      |   type  | default |                   description                    |
    |-------------------|--------------------|---------|---------|--------------------------------------------------|
    | tag               | :x:                | string  | ul      |                                                  |
    | delay             | :white_check_mark: | number  |         | in milliseconds                                  |
    | beforeEnterStyles | :white_check_mark: | object  |         | [props][velo]                                    |
    | enterStyles       | :white_check_mark: | object  |         | [props][velo]                                    |
    | leaveStyles       | :white_check_mark: | object  |         | [props][velo]                                    |
    | options           | :x:                | object  | {}      | extra velocity [options][opt]                    |
    | enterAtOnce       | :x:                | boolean | false   | show all items at once "dont delay the entering" |
    | leaveAtOnce       | :x:                | boolean | false   | hide all items at once "dont delay the leaving"  |

    [velo]: http://velocityjs.org/#cssSupport
    [opt]: http://velocityjs.org/
