<template>
  <div>
    <nav-menu />

    <div class="ui vertical stripe segment main-body">
      <div class="ui middle aligned stackable grid container">
        <div v-if="commitData" style="width:100%">
          <heatmap :commits="commitData.contribution" :user="commitData.team" :max="max" />
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
      dataUrl: '/data/team-commits.json',
      commitData: null,
      max: 15
    }
  },
  computed: {},
  created() {
    axios.get(this.dataUrl).then(res => {
      this.commitData = res['data']
    })
  },
  methods: {}
}
</script>

<style></style>
