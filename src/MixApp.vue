<template>
  <div id="app">
    <div class="pusher">
      <div
        class="ui inverted vertical masthead center aligned segment"
        style="background:#056DAE;min-height:30px"
        id="main-menu"
      >
        <div class="ui container">
          <div
            class="ui large secondary inverted pointing menu"
            style="border:0"
          >
            <a class="toc item">
              <i class="sidebar icon"></i>
            </a>
            <router-link class="item" to="/">
              <img id="logo-img" alt="Awesome UI" src="./assets/default.png" />
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

      <div
        class="ui vertical stripe segment"
        style="padding:4em;min-height:670px"
      >
        <div class="ui middle aligned stackable grid container">
          <router-view />
        </div>
      </div>

      <Footer />
    </div>
  </div>
</template>

<script>
import Footer from '@/components/footer.vue'
export default {
  name: 'app',
  data: () => {
    return {
    }
  },
  components: {
    Footer
  },
  computed: {
    routes: function() {
      var routes = []
      for (var i in this.$router.options.routes) {
        var route = this.$router.options.routes[i]
        if(route.kind=='main'){
          routes.push(route)
        }
      }
      return routes
    }
  }
}
</script>

<style>
.hidden.menu {
  display: none;
}

#main-menu {
  background: #056dae;
  background-image: url(/static/images/bg.jpg);
  background-repeat: no-repeat;
  background-size: 100% 100%;
  -moz-background-size: 100% 100%;
  padding-bottom: 40px;
}

#main-menu > .ui.container h2 {
  margin-bottom: 30px;
}

.page-logo {
  width: 50%;
  margin-top: 80px;
  filter: drop-shadow(2px 2px 5px black);
}

#logo-img {
  margin-bottom: -10px;
  width: 35px;
  filter: drop-shadow(1px 1px 3px black);
}

.masthead.segment {
  min-height: 500px;
  padding: 1em 0em;
}

.masthead .logo.item img {
  margin-right: 1em;
}

.masthead .ui.menu .ui.button {
  margin-left: 0.5em;
}

.masthead h1.ui.header {
  margin-top: 1em;
  margin-bottom: 0em;
  font-size: 4em;
  font-weight: normal;
}

.masthead h2 {
  font-size: 1.7em;
  font-weight: normal;
}

.ui.vertical.stripe {
  padding: 8em 0em;
}

.ui.vertical.stripe h3 {
  font-size: 2em;
}

.ui.vertical.stripe .button + h3,
.ui.vertical.stripe p + h3 {
  margin-top: 3em;
}

.ui.vertical.stripe .floated.image {
  clear: both;
}

.ui.vertical.stripe p {
  font-size: 1.33em;
}

.ui.vertical.stripe .horizontal.divider {
  margin: 3em 0em;
}

.quote.stripe.segment {
  padding: 0em;
}

.quote.stripe.segment .grid .column {
  padding-top: 5em;
  padding-bottom: 5em;
}

.footer.segment {
  padding: 5em 0em;
}

.secondary.pointing.menu .toc.item {
  display: none;
}

.ui.secondary.pointing.menu .item.text.router-link-exact-active {
  color: #fff !important;
  font-weight: 700 !important;
  border-bottom-color: #fff;
  border-bottom-style: solid;
  border-bottom-width: 2px;
}

body {
  color: #444;
  font-weight: 300;
  line-height: 1.45;
}

@media only screen and (max-width: 700px) {
  .ui.fixed.menu {
    display: none !important;
  }

  .secondary.pointing.menu .item,
  .secondary.pointing.menu .menu {
    display: none;
  }

  .secondary.pointing.menu .toc.item {
    display: block;
  }

  .masthead.segment {
    min-height: 350px;
  }

  .masthead h1.ui.header {
    font-size: 2em;
    margin-top: 1.5em;
  }

  .masthead h2 {
    margin-top: 0.5em;
    font-size: 1.5em;
  }
}
</style>
