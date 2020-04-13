<template>
  <div class="pusher">
    <div
      class="ui inverted vertical masthead center aligned segment"
      id="main-menu"
    >
      <pure-nav />

      <div class="ui container">
        <img class="page-logo" src="../assets/dogops.png" />
        <!-- <h1 class="ui inverted header">{{name}} </h1>-->
        <h2>{{ subtitle }}</h2>
        <span v-for="i in entries" :key="i.key">
          hello
        </span>
      </div>
    </div>

    <div class="ui vertical stripe segment">
      <div class="ui middle aligned stackable grid container">
        <div class="row">
          <div class="eight wide column">
            <div
              v-for="i in introductions"
              style="margin-top:30px"
              :key="i.key"
            >
              <h3 class="ui header">{{ i.name }}</h3>
              <p>{{ i.desc }}</p>
            </div>
          </div>
          <div class="six wide right floated column">
            <img
              src="../assets/dogops.png"
              class="ui large bordered rounded image"
            />
          </div>
        </div>
        <div class="row">
          <div class="center aligned column">
            <a class="ui huge button" :href="learnMore.url">{{
              learnMore.name
            }}</a>
          </div>
        </div>
      </div>
    </div>

    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src

import Footer from '@/components/footer.vue'
import PureNav from '@/components/pureNav.vue'

export default {
  name: 'Home',
  components: { Footer, PureNav },
  data: () => {
    return {
      subtitle:
        'Move fast and don\'t break things, win the "Time to Market" battle.',

      introductions: [
        {
          name: 'Continuous Delivery',
          desc:
            'With continuous delivery, every code change is built, tested, and then pushed to a non-production testing or staging environment.'
        },
        {
          name: 'Automate Everything',
          desc:
            'In DevOps, automation kick starts from the code generation on Developers machine till the code is pushed to the code and even after that to monitor the application and system in production.'
        }
      ],
      learnMore: {
        name: 'Learn More',
        url: ''
      }
    }
  },
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
