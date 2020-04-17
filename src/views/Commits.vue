<template>
  <div>
    <nav-menu />

    <div class="ui vertical stripe segment main-body">
      <div class="ui middle aligned stackable grid container">
        <heatmap :commits="commits" :user="user" />
        <heatmap :commits="commitData" :user="user" />
        {{ commitData }}
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
  name: 'app',
  data: () => {
    return {
      user: 'Toby Qin',
      dataUrl: 'http://127.0.0.1:5500/github-commit.json',
      commitData:null
    }
  },
  methods:{
    getData(){
      axios.get(this.dataUrl).then((res)=>{
        this.commitData=res
      })
    }
  },
  components: { NavMenu, Foot, Heatmap },
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
  created(){
    var dataUrl='http://127.0.0.1:5500/github-commit.json'
    this.commitData =[]
    axios.get(dataUrl).then((res)=>{
        var data=res['data']
        for(var c of data){
          c['count']=c['commits']
          this.commitData.push(c)
        }
        
      })
  }
}
</script>

<style></style>
