<template>
	<div class="card text-center">
		<div class="img-container">
			<img :src="imgUrl" alt="" />
		</div>
		<h2>{{ title }}</h2>
		<h5>{{ author }}</h5>
		<h6>{{ year }}</h6>
	</div>
</template>

<script>
export default {
	name: "Card",
	props: {
		imgUrl: String,
		title: String,
		author: String,
		year: String
	}
};
</script>

<style lang="scss" scoped>
@import "../style/variables";
.card {
	height: 100%;
	background-color: $mainGrey;
	.img-container {
		padding: 20px;
		img {
			width: 100%;
		}
	}
	h2 {
		color: white;
		text-transform: uppercase;
		font-weight: 500;
		font-size: 24px;
	}
	h5,
	h6 {
		font-weight: 400;
		color: grey;
	}
}
</style>
