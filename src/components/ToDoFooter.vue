<template>
	<div class="clearAllContainer">
		<span class="clearAllBtn" v-on:click="clearTodo">Clear All</span>
	</div>
	<span>하단 푸터</span>
</template>

<script>
import { mapMutations } from "vuex";

export default {
	methods: {
		...mapMutations({
			clearTodo: "clearAllItems",
		}),
	},
};
</script>

<style scoped>
.clearAllContainer {
	width: 8.5rem;
	height: 50px;
	line-height: 50px;
	background-color: #ffffff;
	border-radius: 5px;
	margin: 0 auto;
	cursor: pointer;
}
.clearAllBtn {
	color: #e20303;
	display: block;
}
</style>
