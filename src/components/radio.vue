<template>
<div id="example-2">
	<label v-for="(item, index) in items" :for="index">
  	<input type="radio" :id="index" :value="index" v-model="picked">
  </label>
<span>{{picked}}</span>
</div>
</template>

<script>
// import Vue from 'vue'

// var example2 = new Vue({
//   el: '#example-2',
//   data: {
//     parentMessage: 'Parent',
//     items: [
//       { message: 'Foo' },
//       { message: 'Bar' }
//     ]
//   }
// })

export default ({
	name: 'radio',
	data () {
		return {
			parentMessage: 'Parent',
      items: [
        { message: 'Foo' },
        { message: 'Bar' }
      ]
		}
	},
	methods: {
		picked: 'picked'
	}
})
</script>

<style>

</style>