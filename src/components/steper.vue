<template>
  <div class="hello">
    <h3 class="ui center aligned header">{{ msg }}</h3>
    <br>
    <div class="ui last container">
      <div class="ui three steps">
        <div class="step">
          <div class="content">
            <div class="title">Shipping</div>
            <div class="description">Choose your shipping options</div>
          </div>
        </div>
        <div class="active step">
          <div class="content">
            <div class="title">Billing</div>
            <div class="description">Enter billing information</div>
          </div>
        </div>
        <div class="disabled step">
          <div class="content">
            <div class="title">Confirm Order</div>
            <div class="description">Review your order details</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Steper',
  props: {
    msg: { type: String, default: 'hello' }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
