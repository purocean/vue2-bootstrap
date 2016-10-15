<template>
  <div :class="['dropdown', {open: show, disabled: disabled}]" >
    <button type="button" :class="['btn', 'btn-' + type, 'dropdown-toggle']" :disabled="disabled" @click="toggle" @keyup.esc="show = false" @blur="show = false">
      {{ text }}
      <span class="caret"></span>
    </button>
    <slot name="dropdown-menu">
      <ul class="dropdown-menu" @click="show = false">
        <slot></slot>
      </ul>
    </slot>
  </div>
</template>

<script>
export default {
  props: {
    isShow: {
      type: Boolean,
      default: false
    },
    isDisabled: {
      type: Boolean,
      default: false
    },
    text: {
      type: String,
      default: null
    },
    type: {
      type: String,
      default: 'default'
    }
  },
  data () {
    return {
      show: this.isShow,
      disabled: this.isDisabled
    }
  },
  computed: {
  },
  methods: {
    toggle () {
      this.show = !this.show
    }
  },
  ready () {
  },
  beforeDestroy () {
  }
}
</script>

<style scoped>
</style>
