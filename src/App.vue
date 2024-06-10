<template>
	<div>
		<div v-for="(v, i) in products" :key="i">
			<h4>{{ v.product }}</h4>
			<p>{{ v.price }} 만원</p>
			<button @click="increase(i)">구매</button> <span>구매수 : {{ v.purchaseCount }}</span>
		</div>
	</div>
</template>

<script>
import products from "/src/assets/products.js";

export default {
	name: "App",
	data() {
		return {
			modalOpen: false,
			products,
		};
	},
	methods: {
		increase(i) {
			this.products[i].purchaseCount++;
		},
	},
	components: {},
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
