<template>
	<div id="app">
		<Header :arrayTornatoPieno="discArray" />
		<Main @passoArrayPieno="riempiArrayApp" />
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
			discArray: []
		};
	},
	methods: {
		prova(arrayVuoto) {
			console.log("Ciao da App", arrayVuoto);
			this.$emit("richiamoMain", arrayVuoto);
		},
		riempiArrayApp(discArray) {
			this.discArray = discArray;
		}
	}
};
</script>

<style lang="scss">
@import "./style/general";
</style>
