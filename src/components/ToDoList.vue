<template>
	<div>
		<transition-group name="list" tag="ul">
			<li v-for="(todoItem, index) in this.storedTodoItems" v-bind:key="todoItem.item" class="shadow">
				<i
					class="fas fa-check checkBtn shadow"
					v-bind:class="{ checkBtnCompleted: todoItem.completed }"
					v-on:click="toggleComplete({ todoItem, index })"
				></i>
				<span v-bind:class="{ textCompleted: todoItem.completed }">
					{{ todoItem.item }}
				</span>
				<span class="removeBtn" v-on:click="removeTodo({ todoItem, index })">
					<i class="fas fa-trash-alt shadow"></i>
				</span>
			</li>
		</transition-group>
	</div>
</template>

<script>
import { mapGetters, mapMutations } from "vuex";

export default {
	computed: {
		...mapGetters(["storedTodoItems"]),
	},
	methods: {
		...mapMutations({
			removeTodo: "removeOneItem",
			toggleComplete: "toggleOneItem",
		}),
	},
};
</script>

<style scoped>
ul {
	list-style-type: none;
	padding-left: 0px;
	margin-top: 0px;
	text-align: left;
}
li {
	display: flex;
	min-height: 45px;
	height: 45px;
	line-height: 45px;
	margin: 0.5rem 0;
	padding: 0 0.9rem;
	background: #ffffff;
	border-radius: 5px;
}
.removeBtn {
	margin-left: auto;
	color: #000000;
}
.checkBtn {
	line-height: 45px;
	color: #62acde;
	margin-right: 5px;
}
.checkBtnCompleted {
	color: #b3adad;
}
.textCompleted {
	text-decoration: line-through;
	color: #b3adad;
}
i {
	cursor: pointer;
}
/* 리스트 아이템 트렌지션 효과 */
.list-enter-active,
.list-leave-active {
	transition: all 1s;
}
.list-enter, .list-leave-to /* .list-leave-active below version 2.1.8 */ {
	opacity: 0;
	transform: translateY(30px);
}
</style>
