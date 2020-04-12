<template>
  <div class="home">
    <Steper msg="Get started with Vue.js" />
  </div>
</template>

<script>
// @ is an alias to /src
import Steper from '@/components/steper.vue'

export default {
  name: 'Home',
  data: () => {
    return {
    }
  },
  components: {
    Steper
  }
}
</script>
