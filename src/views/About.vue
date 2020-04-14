<template>
  <div>
    <nav-menu />

    <div
      class="ui vertical stripe segment main-body"
    >
      <div class="ui middle aligned stackable grid container">
        <h3 class="ui center aligned header">Container</h3>
        <div class="ui container">
          <div class="ui segments">
            <div class="ui segment">Content</div>
            <div class="ui segment">Content</div>
            <div class="ui segment">Content</div>
            <div class="ui segment">Content</div>
          </div>
        </div>
      </div>
    </div>

    <foot />
  </div>
</template>

<script>
import NavMenu from '@/components/navMenu.vue'
import Foot from '@/components/footer.vue'
export default {
  name: 'app',
  data: () => {
    return {}
  },
  components: { NavMenu, Foot },
  computed: {}
}
</script>
