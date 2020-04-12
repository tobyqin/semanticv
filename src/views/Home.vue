<template>
  <div class="home">
    <Step msg="Get started with Vue.js"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Step from '@/components/steper.vue'

export default {
  name: 'Home',
  components: {
    Step
  }
}
</script>
