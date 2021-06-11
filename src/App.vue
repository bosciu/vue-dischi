<template>
	<div id="app">
		<Header
			:arrayGeneraleTornatoPieno="arrayGenerale"
			@passoValore="salvoValore"
		/>
		<Main
			@passoArrayGenerale="salvoArrayGenerale"
			:valoreSelezionato="valoreSelezionato"
			:chiaveSelect="chiaveSelect"
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
			valoreSelezionato: undefined,
			chiaveSelect: "all",
			arrayGenerale: []
		};
	},
	methods: {
		salvoValore(valore, chiaveSelect) {
			this.valoreSelezionato = valore;
			if (chiaveSelect != undefined) {
				this.chiaveSelect = chiaveSelect;
			}
		},
		salvoArrayGenerale(array) {
			this.arrayGenerale = array;
		}
	}
};
</script>

<style lang="scss">
@import "./style/general";
</style>
