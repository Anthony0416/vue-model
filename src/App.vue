<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <!-- <p @click="vueAlert">这段文字用于触发点击事件</p> -->
    <!-- <Alert v-show="cont">这里是内容</Alert> -->
    <vueButton size='big'>确认</vueButton>
    <radio></radio>
    <div style="height:10000px"></div>
  </div>
</template>

<script>
// import Alert from './components/vue-alert.vue'
import $ from 'jquery'
import vueButton from './components/vue-button.vue'
import radio from './components/radio.vue'

export default {
  name: 'app',
  data () {
    return {
      // cont: true,
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    // vueAlert: function(){
    //   $('body').css("overflow-y","hidden");
    // }
  },
  components: {vueButton,radio}
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
