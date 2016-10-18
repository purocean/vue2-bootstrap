<template>
  <nav :class="['navbar',{
    'navbar-inverse':(type == 'inverse'),
    'navbar-default':(type == 'default'),
    'navbar-fixed-top':(placement === 'top'),
    'navbar-fixed-bottom':(placement === 'bottom'),
    'navbar-static-top':(placement === 'static')
  }]">
    <div class="container-fluid">
      <div class="navbar-header">
        <button type="button" class="navbar-toggle collapsed"  aria-expanded="false" @click="toggleCollapse">
          <span class="sr-only">Toggle navigation</span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>
        <slot name="brand"></slot>
      </div>
      <div :class="['navbar-collapse', {collapse: collapsed}]">
        <ul class="nav navbar-nav">
          <slot></slot>
        </ul>
        <ul v-if="slots.right" class="nav navbar-nav navbar-right">
          <slot name="right"></slot>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: 'default'
    },
    placement: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      collapsed: true,
    }
  },
  computed: {
    slots () {
      return this.$slots
    }
  },
  methods: {
    toggleCollapse (e) {
      e && e.preventDefault()
      this.collapsed = !this.collapsed
    }
  },
  created () {
  },
  ready () {
  },
  beforeDestroy () {
  }
}
</script>
