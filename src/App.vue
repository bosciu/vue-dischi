<template>
	<div id="app">
		<Header @richiamoApp="prova" :arrayTornatoPieno="arrayVuoto" />
		<Main @passoArrayPieno="prova1" :arrayVuoto="arrayVuoto" />
	</div>
</template>

<script>
import Header from "./components/Header";
import Main from "./components/Main";
export default {
	name: "App",
	components: {
		Header,
		Main
	},
	data() {
		return {
			arrayVuoto: []
		};
	},
	methods: {
		prova(arrayVuoto) {
			console.log("Ciao da App", arrayVuoto);
			this.$emit("richiamoMain", arrayVuoto);
		},
		prova1(discArray) {
			this.arrayVuoto = discArray;
		}
	}
};
</script>

<style lang="scss">
@import "./style/general";
</style>
