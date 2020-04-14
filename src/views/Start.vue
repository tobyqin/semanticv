<template>
  <div>
    <nav-menu />

    <div class="ui vertical stripe segment main-body">
      <div class="ui middle aligned stackable grid container">
        <Steper />
      </div>
    </div>

    <foot />
  </div>
</template>

<script>
import NavMenu from '@/components/navMenu.vue'
import Foot from '@/components/footer.vue'
import Steper from '@/components/steper.vue'
export default {
  name: 'app',
  data: () => {
    return {}
  },
  components: { NavMenu, Foot, Steper },
  computed: {}
}
</script>

<style>

</style>
