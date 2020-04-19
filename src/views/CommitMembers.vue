<template>
  <div>
    <nav-menu />

    <div class="ui vertical stripe segment main-body">
      <div class="ui middle aligned stackable grid container">
        <div v-if="commitData" style="width:100%">
          <heatmap v-for="c in commitData" :key="c.key" :commits="c.contribution" :user="c.user" />
        </div>
      </div>
    </div>

    <foot />
  </div>
</template>

<script>
import NavMenu from '@/components/navMenu.vue'
import Foot from '@/components/footer.vue'
import Heatmap from '@/components/heatmap.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: { NavMenu, Foot, Heatmap },
  data: () => {
    return {
      dataUrl: '/data/member-commits.json',
      commitData: []
    }
  },
  computed: {},
  created() {
    this.commitData = []
    axios.get(this.dataUrl).then(res => {
      var data = res['data']
      for (var c of data) {
        c['count'] = c['commits']
        this.commitData.push(c)
      }
    })
  },
  methods: {}
}
</script>

<style></style>
