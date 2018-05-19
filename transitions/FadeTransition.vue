<template>
  <component :is="component"
    name="fade-stack"
    tag="div"
    :css="false"
    @beforeEnter="beforeEnter"
    @enter="enter"
    @leave="leave"
    v-on="$listeners"
    v-bind="$attrs">
    <slot />
  </component>
</template>

<script>
  export default {
    name: 'fade-transition',
    props: {
      duration: {
        type: Number,
        default: 400
      },
      delay: {
        type: Number,
        default: 50
      },
      group: {
        type: Boolean,
        default: true
      }
    },
    computed: {
      component () {
        return this.group ? 'transition-group' : 'transition'
      }
    },
    methods: {
      beforeEnter (el) {
        el.style.opacity = 0
      },
      enter (el, done) {
        setTimeout(() => {
          this.$velocity(
            el,
            {
              opacity: 1,
              transform: ['translateY(0px)', 'translateY(-10px)']
            },
            {
              duration: this.duration,
              complete: done
            }
          )
        }, el.dataset.index * this.delay)
      },
      leave (el, done) {
        setTimeout(() => {
          this.$velocity(
            el,
            {
              opacity: 0,
              transform: 'translateY(+10px)'
            },
            {
              duration: this.duration,
              complete: done
            }
          )
        }, el.dataset.index * this.delay)
      }
    }
  }
</script>

