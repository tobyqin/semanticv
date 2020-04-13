<template>
  <div>
    <div
      class="ui inverted vertical masthead center aligned segment"
      style="background:#056DAE;min-height:30px"
      id="main-menu"
    >
      <pure-nav />
    </div>
  </div>
</template>

<script>
import pureNav from './pureNav.vue'
export default {
  name: 'Nav',
  components: { pureNav },
  props: {
    routes: Object
  }
}
</script>
