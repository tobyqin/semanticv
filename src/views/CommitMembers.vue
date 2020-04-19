<template>
  <el-container class="root">
    <el-header height="100px">
      <my-menu />
    </el-header>
    <el-main>
      <div style="margin:2em">
        <div v-if="commitData" style="width:100%">
          <heatmap v-for="c in commitData" :key="c.key" :commits="c.contribution" :user="c.user" />
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
