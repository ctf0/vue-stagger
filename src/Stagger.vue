<template>
    <transition-group
        :css="false"
        :tag="tag"
        @before-enter="beforeEnter"
        @enter="enter"
        @leave="leave">

        <slot/>
    </transition-group>
</template>

<script>
import Velocity from 'velocity-animate'

export default {
    name: 'transition-stagger',
    props: {
        tag: {
            type: String,
            required: false,
            default: 'ul'
        },
        delay: {
            type: Number,
            required: true
        },
        beforeEnterStyles: {
            type: Object,
            required: true
        },
        enterStyles: {
            type: Object,
            required: true
        },
        leaveStyles: {
            type: Object,
            required: true
        }
    },
    data() {
        return Object.assign({
            count: 0
        }, this.$parent.$data, this.$parent.$props)
    },
    methods: {
        beforeEnter(el) {
            Object.assign(el.style, this.beforeEnterStyles)
        },
        enter(el, done) {
            this.animate(el, done, this.enterStyles)
        },
        leave(el, done) {
            this.count = 0
            this.animate(el, done, this.leaveStyles)
        },
        animate(el, done, styles) {
            this.count++

            return setTimeout(() => {
                Velocity(
                    el,
                    styles,
                    {complete: done}
                )
            }, this.count * this.delay)
        }
    }
}
</script>
