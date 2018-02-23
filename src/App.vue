<template lang="pug">
	<test-app></test-app>
</template>

<script>
import Test from './test.vue';
export default {
	name: 'main-app',
	data() {
		return {
			msgs: 'Components 😑'
		}
	},
	components: {
		'test-app': Test
	}
}
</script>