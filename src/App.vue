<template>
	<div id="app">
		<Header :arrayTornatoPieno="genreArray" @passoGenere="salvoGenere" />
		<Main
			@passoArrayGeneri="riempiArrayApp"
			:genereSelezionato="genereSelezionato"
		/>
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
			genreArray: [],
			genereSelezionato: undefined
		};
	},
	methods: {
		riempiArrayApp(genreArray) {
			this.genreArray = genreArray;
		},
		salvoGenere(genere) {
			this.genereSelezionato = genere;
			console.log(genere);
		}
	}
};
</script>

<style lang="scss">
@import "./style/general";
</style>
