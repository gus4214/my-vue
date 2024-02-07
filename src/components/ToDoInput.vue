<template>
	<div>
		<input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" />
		<span class="addContainer" v-on:click="addTodo">
			<i class="fas fa-plus addBtn"></i>
		</span>
	</div>
</template>

<script>
export default {
	data() {
		return {
			newTodoItem: "",
			showModal: false,
		};
	},
	methods: {
		addTodo() {
			if (this.newTodoItem != "") {
				this.$store.commit("addOneItem", this.newTodoItem.trim());
				this.clearInput();
			} else {
				this.showModal = !this.showModal;
			}
		},
		clearInput() {
			this.newTodoItem = "";
		},
	},
};
</script>
