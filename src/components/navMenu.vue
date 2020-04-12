<template>
  <div>
    <div
      class="ui inverted vertical masthead center aligned segment"
      style="background:#056DAE;min-height:30px"
      id="main-menu"
    >
      <div class="ui container">
        <div class="ui large secondary inverted pointing menu" style="border:0">
          <a class="toc item">
            <i class="sidebar icon"></i>
          </a>
          <router-link class="item" to="/">
            <img id="logo-img" alt="Awesome UI" src="../assets/default.png" />
          </router-link>
          <router-link
            :to="route.path"
            v-for="route in routes"
            :key="route.key"
            class="item text"
          >
            {{ route.name }}
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  props: {
    routes: Object
  }
}
</script>
