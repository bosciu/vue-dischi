<template>
	<header class="d-flex">
		<img src="../assets/logo.png" alt="Spotify" />
		<div class="selects d-flex">
			<Select
				main-text="Seleziona un genere"
				:optionArray="arrayGeneraleTornatoPieno"
				:chiave-select="chiaveSelect1"
				@selectOptionReturn="passoValore"
			/>
			<Select
				main-text="Seleziona l'artista"
				:optionArray="arrayGeneraleTornatoPieno"
				:chiave-select="chiaveSelect2"
				@selectOptionReturn="passoValore"
			/>
		</div>
	</header>
</template>

<script>
import Select from "./Select";
export default {
	name: "Header",
	components: {
		Select
	},
	data() {
		return {
			chiaveSelect1: "genre",
			chiaveSelect2: "author"
		};
	},
	props: {
		arrayGeneriTornatoPieno: Array,
		arrayGeneraleTornatoPieno: Array
	},
	methods: {
		passoValore(valore, chiaveSelect) {
			this.$emit("passoValore", valore, chiaveSelect);
		}
	}
};
</script>

<style lang="scss" scoped>
@import "../style/variables";
header {
	justify-content: space-between;
	height: 100px;
	padding: 15px;
	background-color: $mainGrey;
	.selects {
		width: 25%;
	}
	img {
		height: 100%;
	}
}
</style>
