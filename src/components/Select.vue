<template>
	<select
		class="form-select"
		@change="
			$emit('changeGenre', arrayDischi);
			riempiArray;
		"
	>
		<option selected>{{ mainText }}</option>
		<option
			v-for="(oggetto, index) in arrayTornatoPieno"
			:key="index"
			value="1"
		>
			{{ oggetto.genre }}
		</option>
	</select>
</template>

<script>
export default {
	name: "Select",
	props: {
		mainText: String,
		arrayTornatoPieno: Array
	},
	data() {
		return {
			arrayDischi: []
		};
	},
	methods: {
		riempiArray() {
			this.arrayDischi = this.arrayTornatoPieno;
			console.log(this.arrayDischi);
		}
	}
};
</script>

<style lang="scss" scoped>
.form-select {
	align-self: center;
	width: 210px;
	height: 80%;
	margin-left: auto;
}
</style>
