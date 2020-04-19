<template>
  <el-row class="my-footer">
    <el-col :span="4">
      <div>
        <h4>Contact us</h4>
        <ul>
          <li v-for="item in footer.contact" :key="item.id">
            <a :href="item.href">{{ item.name }}</a>
          </li>
        </ul>
      </div>
    </el-col>
    <el-col :span="4">
      <div>
        <h4>More about</h4>
        <ul>
          <li v-for="item in footer.more" :key="item.id">
            <a :href="item.href">{{ item.name }}</a>
          </li>
        </ul>
      </div>
    </el-col>
    <el-col :span="8">
      <div>
        <h4>{{ footer.about.name }}</h4>
        <p v-html="footer.about.desc" />
      </div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: 'PageFooter',
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
.my-footer {
  background-color: #1b1c1d;
  color: #eee;
  min-height: 100px;
  padding: 30px;
}
.my-footer  ul {
  padding-left: 0em;
}

.my-footer ul li{
  list-style: none;
}

.my-footer ul li a{
  color: #bbb;
}
</style>
