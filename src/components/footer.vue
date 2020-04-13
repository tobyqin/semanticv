<template>
  <div class="ui inverted vertical footer segment" id="main-footer">
    <div class="ui container">
      <div class="ui stackable inverted divided equal height stackable grid">
        <div class="three wide column">
          <h4 class="ui inverted header">Contact us</h4>
          <div class="ui inverted link list">
            <a
              v-for="item in footer.contact"
              :href="item.url"
              class="item"
              :key="item.id"
            >
              {{ item.name }}
            </a>
          </div>
        </div>
        <div class="three wide column">
          <h4 class="ui inverted header">More about</h4>
          <div class="ui inverted link list">
            <a
              v-for="item in footer.more"
              :href="item.url"
              class="item"
              :key="item.id"
            >
              {{ item.name }}
            </a>
          </div>
        </div>
        <div class="seven wide column">
          <h4 class="ui inverted header">{{ footer.about.name }}</h4>
          <p v-html="footer.about.desc"></p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'footer',
  props: {},
  data: function() {
    return {
      footer: {
        contact: [
          {
            name: 'Email',
            url: 'mailto:toby.qin@me.com'
          },
          {
            name: 'Skype',
            url: 'sip:toby.qin@me.com'
          }
        ],
        more: [
          {
            name: 'Pipeline',
            url: ''
          },
          {
            name: 'APIs',
            url: '/api/'
          }
        ],
        about: {
          name: 'DEVOPS',
          desc:
            'This site is initialized and maintained by <a href="https://github.com/tobyqin">Toby Qin</a>, welcome to contribute your thoughts and suggestions.'
        }
      }
    }
  }
}
</script>

<style>
body{

}
#main-footer {

}
</style>
