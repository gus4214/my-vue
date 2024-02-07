<template>
	<div id="app">
		<ToDoTitle />
		<ToDoInput />
	</div>
</template>

<script>
import ToDoTitle from "../src/components/ToDoTitle";
import ToDoInput from "./components/ToDoInput.vue";

export default {
	name: "App",
	components: {
		ToDoTitle,
		ToDoInput,
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
