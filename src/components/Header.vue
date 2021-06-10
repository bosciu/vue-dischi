<template>
	<header class="d-flex">
		<img src="../assets/logo.png" alt="Spotify" />
		<Select
			main-text="Seleziona un genere"
			:arrayTornatoPieno="arrayTornatoPieno"
		/>
	</header>
</template>

<script>
import Select from "./Select";
export default {
	name: "Header",
	components: {
		Select
	},
	props: {
		arrayTornatoPieno: Array
	}
};
</script>

<style lang="scss" scoped>
@import "../style/variables";
header {
	height: 100px;
	padding: 15px;
	background-color: $mainGrey;
	img {
		height: 100%;
	}
}
</style>
