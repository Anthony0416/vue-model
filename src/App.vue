<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <p @click="vueAlert">这段文字用于触发点击事件</p>
    <Alert v-show="cont">这里是内容</Alert>
    <div style="height:10000px"></div>
  </div>
</template>

<script>
import vue from 'vue'
import Alert from './components/vue-alert.vue'
import $ from 'jquery'

var app = new vue({
  el: '#app',
  data: {
    cont: true
  }
})

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    vueAlert: function(){
      alert(app.alert);
    }
  },
  components: {Alert}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}
</style>
