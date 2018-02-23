<template lang="pug">
	#main-app
		.main-content
			p {{msgs}}
			h6 Name:
			input(type="text" value="" v-model="name")
			br
			label Guests 
			input(type="button" 
						class="btn btn-primary" 
						value="+"
						v-on:click="addGuest")
			.add-guest(v-for="(guest, index) in guests")
				label(v-on:click="deleteGuest(index)") Guest <span>#</span>{{index + 1}}
				input(class="guest" type="text" v-model="guests[index]")
			.list
				ul
					li(v-for="(guest, index) in guests") {{ guest }}
			p.hello Helloworld
</template>


<script>
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
	}
}
</script>

<style>

</style>
