<template>
	<div id="app">
		<Header :arrayTornatoPieno="genreArray" />
		<Main @passoArrayGeneri="riempiArrayApp" />
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
			genreArray: []
		};
	},
	methods: {
		riempiArrayApp(genreArray) {
			this.genreArray = genreArray;
		}
	}
};
</script>

<style lang="scss">
@import "./style/general";
</style>
