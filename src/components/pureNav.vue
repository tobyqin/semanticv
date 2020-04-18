<template>
  <div>
    <div class="ui container">
      <div class="ui large secondary inverted pointing menu" style="border:0">
        <a class="toc item">
          <i class="sidebar icon" />
        </a>
        <router-link class="item" to="/">
          <img id="logo-img" alt="Awesome UI" src="../assets/default.png">
        </router-link>
        <router-link v-for="route in mainRoutes" :key="route.key" :to="route.path" class="item text">
          {{ route.name }}
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PurNav',
  computed: {
    mainRoutes: function() {
      var routes = []
      for (var i in this.$router.options.routes) {
        var route = this.$router.options.routes[i]
        if (route.kind === 'main') {
          routes.push(route)
        }
      }
      return routes
    }
  }
}
</script>
