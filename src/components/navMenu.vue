<template>
  <div
    id="main-menu"
    class="ui inverted vertical masthead center aligned segment"
    style="background:#056DAE;min-height:30px"
  >
    <pure-nav />
  </div>
</template>

<script>
import pureNav from './pureNav.vue'
export default {
  name: 'Nav',
  components: { pureNav },
  props: {
    routes: { type: Object, default: null }
  }
}
</script>
