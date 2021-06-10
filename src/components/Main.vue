<template>
	<main>
		<transition name="fade">
			<Loader v-if="!isLoaded" />
		</transition>
		<div else class="container">
			<div class="row">
				<div
					class="col-6 col-md-4 col-lg-2"
					v-for="(disc, index) in discArray"
					:key="index"
				>
					<Card
						:img-url="disc.poster"
						:title="disc.title"
						:author="disc.author"
						:year="disc.year"
					/>
				</div>
			</div>
		</div>
	</main>
</template>

<script>
import Card from "./Card";
import Loader from "./Loader";
import axios from "axios";
export default {
	name: "Main",
	components: {
		Card,
		Loader
	},
	data() {
		return {
			discArray: [],
			isLoaded: false
		};
	},
	created() {
		axios
			.get("https://flynn.boolean.careers/exercises/api/array/music")
			.then((response) => {
				response.data.response.forEach((element) => {
					this.discArray.push(element);
				});
				setTimeout(() => {
					this.isLoaded = true;
				}, 1500);
			});
	}
};
</script>

<style lang="scss" scoped>
@import "../style/variables";
main {
	padding-top: 5%;
	min-height: calc(100vh - #{$headerHeight});
	background-color: $mainBlue;
	.row {
		justify-content: center;
		& > div {
			margin: 1% 1%;
		}
	}
}
.fade-leave-active {
	transition: opacity 0.7s;
}
.fade-leave-to {
	opacity: 0;
}
</style>
