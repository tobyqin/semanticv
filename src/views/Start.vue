<template>
  <div>
    <nav-menu />
    <br />

    <div class="ui vertical stripe segment main-body">
      <div class="ui middle aligned stackable grid container">
        <Steper />
        <el-button>Hello</el-button>
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
  name: 'App',
  components: { NavMenu, Foot, Steper },
  data: () => {
    return {}
  },
  computed: {}
}
</script>

<style></style>
