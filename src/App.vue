<template>
	<div id="main-app">
		<p>{{msgs}}</p>
		<button v-on:click="clk">Click</button>
		<p>{{count}}</p>
		<!-- <test-app></test-app> -->
	</div>
</template>

<script>
// import Test from './test.vue';
export default {
	name: 'main-app',
	data() {
		return {
			msgs: 'Components 😑',
			count: 0
		}
	},
	methods: {
		clk : function(){
			this.$data.count = this.$data.count + 1;
		}
	},
	// components: {
	// 	'test-app': Test
	// }
}
</script>

<style>

</style>
