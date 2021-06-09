<template>
	<div class="card">
		<div class="img-container">
			<img :src="imgUrl" alt="" />
		</div>
	</div>
</template>

<script>
export default {
	name: "Card",
	props: {
		imgUrl: String
	}
};
</script>

<style lang="scss" scoped>
@import "../style/variables";
.card {
	height: 300px;
	background-color: $mainGrey;
	img {
		width: 100%;
	}
}
</style>
