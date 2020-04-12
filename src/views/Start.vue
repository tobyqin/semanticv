<template>
  <div>
    <Nav :routes="routes"></Nav>

    <div
      class="ui vertical stripe segment"
      style="padding:4em;min-height:670px"
    >
      <div class="ui middle aligned stackable grid container">
        <Steper />
      </div>
    </div>

    <Footer />
  </div>
</template>

<script>
import Nav from '@/components/navMenu.vue'
import Footer from '@/components/footer.vue'
import Steper from '@/components/steper.vue'
export default {
  name: 'app',
  data: () => {
    return {}
  },
  components: { Nav, Footer,Steper },
  computed: {
    routes: function() {
      var routes = []
      for (var i in this.$router.options.routes) {
        var route = this.$router.options.routes[i]
        if (route.kind == 'main') {
          routes.push(route)
        }
      }
      return routes
    }
  }
}
</script>
