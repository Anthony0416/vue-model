<template>
	<div id="vue-alert">
		<div class="alert-box">
			<p class="alert-title">我是子组件的标题</p>
		  <slot>
		    只有在没有内容时才会显示。
		  </slot>
		</div>
	</div>
</template>

<script>

export default {
  name: 'vue-alert',
  data () {
    return {
    }
  }
}

</script>

<style>
body {
	margin: 0;
	padding: 0;
	overflow-y: hidden;
}
#vue-alert {
	position: absolute;
	top: 0;
	width: 100%;
	height: 100%;
	background: rgba(0,0,0,0.3);
}
.alert-box {
	width: 30%;
	background: rgba(0,0,0,0.5);
	padding-bottom: 20px;
	position: absolute;
	top: 45%;
	margin-left: -15%;
	left: 50%;
	color: #FFF;
	border-radius: 5px 
}
.alert-title {
	font-size: 1.6em;
}
</style>