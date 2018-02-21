<template>
	<div id="main-app">
		<div class="main-content">	

		<h6>Name:</h6>
		<input type="text" value="" v-model="name"><br>

		<label>Guests</label>
		<input type="button" 
			class="btn btn-primary" 
			value="+"
			v-on:click="addGuest"
		>
			<div v-for="(guest, index) in guests" class="add-guest">
				<label v-on:dblclick="deleteGuest(index)">Input № {{ index + 1 }}</label>    
				<input class="guest" type="text" v-model="guests[index]">
			</div>
			<div class="guest-list">
				<ul>
					<li v-for="(guest, index) in guests">{{ guest }}</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
// import Test from './test.vue';
export default {
	name: 'main-app',
	data() {
		return {
			msgs: 'Components 😑',
			count: 0,
			name: '',
			guests: []
		}
	},
	methods: {
		clk(){
			this.$data.count = this.$data.count + 1;
		},
		addGuest() {
			this.guests.push('');
			console.log("add");
		},
		deleteGuest(index){
        this.guests.splice(index, 1);
				console.log("delete");
    }
	},
	// components: {
	// 	'test-app': Test
	// }
}
</script>

<style>
.btn {
	margin: 10px 0;
}
.main-content {
	padding: 15px;
}
.add-guest {
	margin: 10px 0;
}
</style>
