<template>
  <el-container class="root">
    <el-header height="100px">
      <my-menu />
    </el-header>
    <el-main>
      <div style="margin:2em">
        <div v-if="commitData" style="width:100%">
          <heatmap :commits="commitData.contribution" :user="commitData.team" :max="max" />
        </div>
      </div>
    </el-main>
    <el-footer>
      <my-foot />
    </el-footer>
  </el-container>
</template>

<script>
import MyMenu from '@/components/MyNav.vue'
import MyFoot from '@/components/MyFooter.vue'
import Heatmap from '@/components/heatmap.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: { MyMenu, MyFoot, Heatmap },
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

<style>
.el-header {
  padding: 0;
}
.el-main {
  padding: 0;
  min-height: 70vh;
}
.el-footer {
  padding: 0;
}
</style>
