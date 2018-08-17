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
        },
        options: {
            type: Object,
            required: false,
            default() {
                return {}
            }
        }
    },
    data() {
        return {
            count: 0
        }
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

            Velocity(
                el,
                styles,
                Object.assign(this.options, {
                    complete: done,
                    delay: this.count * this.delay
                })
            )
        }
    }
}
</script>
