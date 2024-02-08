<template>
	<div id="app">
		<ToDoTitle />
		<ToDoInput />
		<ToDoFooter />
	</div>
</template>

<script>
import ToDoTitle from "../src/components/ToDoTitle";
import ToDoInput from "./components/ToDoInput.vue";
import ToDoFooter from "./components/ToDoFooter.vue";

export default {
	name: "App",
	components: {
		ToDoTitle,
		ToDoInput,
		ToDoFooter,
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}

body {
	display: flex;
	justify-content: center;
}
</style>
