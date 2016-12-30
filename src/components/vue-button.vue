<template>
	<button 
		:class="['vueButton ' + size]" 
	>
		<slot>默认文字</slot>
	</button>
</template>

<script>
	export default {
		name: 'vueButton',
		props: {
			size: {
				type: String,
				default: 'middle',
				validator (value) {
					return [
						'big',
						'small',
						'middle'
					]
				}
			}
		}
	}
</script>

<style>
	.vueButton {
		border: 1px solid #000;
		border-radius: 3px;
		text-align: center;
		cursor: pointer; 
	}
	.big {
		min-width: 150px;
		font-size: 16px;
		padding: 10px 30px;
	}
	.middle{
		min-width: 100px;
		font-size: 14px;
		padding: 5px 10px;
	}
	.small {
		min-width: 50px;
		font-size: 10px;
		padding: 2px 5px;
	}
</style>