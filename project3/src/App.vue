<template>
	hi
	<AppHeader/>
	<div class="w-full flex">
		<!-- <DcHeros/> -->
		<CalendarView/>
	</div>
</template>

<script>
	import AppHeader from "./components/AppHeader.vue";
	// import DcHeros from "./components/DcHeros.vue";
	import CalendarView from "./components/Calendar.vue";

	export default {
		component: {AppHeader,CalendarView},
	}
</script>