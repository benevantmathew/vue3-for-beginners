<template>
	<h1>DC Heros {{ herosCount }}</h1>
	<ul>
		<li v-for="(hero,index) in dcHeros" :key="hero.name">
			<div>
				{{ hero.name }}
				<button @click="remove(index)">x</button>
			</div>				
			
		</li>
	</ul>
	<form @submit.prevent="addHero">
		<input
			v-model.trim="newHero"
			placeholder="Type Hero Name Here"
		/>
		<button>Add Hero</button>
	</form>

</template>

<script>
	export default {
		data() {
			return {
				newHero: "",
				dcHeros: [
					{name:"SuperGirl"},
					{name:'Flash'},
					{name:'Batman'},
					{name:'Arrow'},
					{name:'SuperMan'}
				]
			}
		},
		methods: {
			addHero() {
				if(this.newHero!=""){
					this.dcHeros.push({name:this.newHero});
					this.newHero="";
				}
			},
			remove(index){
				this.dcHeros=this.dcHeros.filter((hero,i)=>i!=index)
			}
		},
		computed: {
			herosCount() {
				return this.dcHeros.length
			}			
		}
	}
</script>