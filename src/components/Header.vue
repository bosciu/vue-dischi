<template>
	<header>
		<img src="../assets/logo.png" alt="Spotify" />
	</header>
</template>

<script>
export default {
	name: "Header"
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
