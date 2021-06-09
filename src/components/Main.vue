<template>
	<main>
		<div class="container">
			<div class="row">
				<div
					class="col-6 col-md-4 col-lg-2"
					v-for="(disc, index) in discArray"
					:key="index"
				>
					<Card :img-url="disc.poster" />
				</div>
			</div>
		</div>
	</main>
</template>

<script>
import Card from "./Card";
import axios from "axios";
export default {
	name: "Main",
	components: {
		Card
	},
	data() {
		return {
			discArray: []
		};
	},
	created() {
		axios
			.get("https://flynn.boolean.careers/exercises/api/array/music")
			.then((response) => {
				response.data.response.forEach((element) => {
					this.discArray.push(element);
				});
			});
	}
};
</script>

<style lang="scss" scoped>
@import "../style/variables";
main {
	height: 1000px;
	background-color: $mainBlue;
}
</style>
