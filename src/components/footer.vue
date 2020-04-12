<template>
  <div class="ui inverted vertical footer segment" id="main-footer">
    <div class="ui container">
      <div class="ui stackable inverted divided equal height stackable grid">
        <div class="three wide column">
          <h4 class="ui inverted header">Contact us</h4>
          <div class="ui inverted link list">
            <a href="" class="item">test</a>
          </div>
        </div>
        <div class="three wide column">
          <h4 class="ui inverted header">More about</h4>
          <div class="ui inverted link list">
            <a href="" class="item">test</a>
          </div>
        </div>
        <div class="seven wide column">
          <h4 class="ui inverted header">name</h4>
          <p>test</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'footer',
  props: {},
  data:function(){
      return {
          footer: {
        contact: [
          {
            name: 'Collaborate',
            url: ''
          },
          {
            name: 'Email',
            url: ''
          },
          {
            name: 'Skype',
            url: ''
          }
        ],
        more: [
          {
            name: 'Pipeline',
            url:
              ''
          },
          {
            name: 'APIs',
            url: '/api/'
          }
        ],
        about: {
          name: 'DEVOPS',
          desc:
            'This site is initialized and maintained by <a href="">Toby Qin</a>, welcome to contribute your thoughts and suggestions.'
        }
      }
      }
  }
}
</script>
