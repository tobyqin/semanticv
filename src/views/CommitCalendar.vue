<template>
  <div>
    <nav-menu />

    <div class="ui vertical stripe segment main-body">
      <div class="ui middle aligned stackable grid container">
        <heatmap v-if="true" :commits="commits" :user="user" />
      </div>
    </div>

    <foot />
  </div>
</template>

<script>
import NavMenu from '@/components/navMenu.vue'
import Foot from '@/components/footer.vue'
import Heatmap from '@/components/heatmap.vue'
export default {
  name: 'App',
  components: { NavMenu, Foot, Heatmap },
  data: () => {
    return {
      user: 'Toby Qin'
    }
  },
  computed: {
    commits() {
      var start = new Date('02/05/2019')
      var end = new Date('02/10/2020')
      var result = []

      var loop = new Date(start)
      while (loop <= end) {
        result.push({ date: loop, count: Math.floor(Math.random() * 6) + 1 })
        var newDate = loop.setDate(loop.getDate() + 1)
        loop = new Date(newDate)
      }
      return result
    }
  },
  created() {},
  methods: {}
}
</script>

<style></style>
