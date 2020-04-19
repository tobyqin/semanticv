<template>
  <div>
    <el-menu
      default-active="/"
      class="el-menu-demo"
      mode="horizontal"
      background-color="#056dae"
      text-color="#ccc"
      active-text-color="#fff"
      :router="routeMode"
    >
      <el-menu-item v-for="route in mainRoutes" :key="route.id" :index="route.path" :route="route">
        {{ route.name }}
      </el-menu-item>
    </el-menu>
  </div>
</template>

<script>
export default {
  name: 'PurNav',
  data: () => {
    return {
      routeMode: true
    }
  },
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
