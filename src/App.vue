<template>
  <div>
    <navbar type="inverse">
      <a slot="brand" href="/" title="Home" class="navbar-brand">Vue Bootstrap</a>
      <li><a>link1</a></li>
      <li><a>link2</a></li>
      <li><a>link3</a></li>
      <li slot="right"><a>link-right1</a></li>
      <li slot="right"><a>link-right2</a></li>
      <li slot="right"><a>link-right3</a></li>
    </navbar>
    <dropdown text="dropdown">
      <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Action</a></li>
      <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Another action</a></li>
      <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Something else here</a></li>
      <li role="presentation"><a role="menuitem" tabindex="-1" href="#">Separated link</a></li>
    </dropdown>
  </div>
</template>

<script>
import {
  Navbar,
  Dropdown
} from './lib.js'
export default {
  components: {
    Navbar,
    Dropdown
  },
  data () {
    return {
    }
  }
}
</script>

<style>
@import '../node_modules/bootstrap/dist/css/bootstrap.css';
</style>
