<template>
	<div class="m-auto">
		<h1 class="text-3xl text-center my-4">Dc Heros {{ herosCount }}</h1>
		<div class="text-center">
			<ul class="border rounded p-2">
			<li
			class="flex justify-between"
			v-for="(hero, index) in dcHeros"
			:key="hero.name"
			>
			<div>
				{{ hero.name }}
			</div>
			<button v-on:click="remove(index)">x</button>
			</li>
			</ul>
			<form class="mt-10" @submit.prevent="addHero">
			<input
			class="border rounded px-2"
			v-model="newHero"
			placeholder="Type Hero Name Here"
			ref="newHeroRef"
			/>
			<button
			class="border rounded bg-gradient-to-r from-red-700 to-pink-500 text-white ml-2 px-2"
			type="submit"
			>
			Add Hero
			</button>
			</form>		
		</div>

	</div>
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