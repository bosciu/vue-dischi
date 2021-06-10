<template>
	<select class="form-select">
		<option selected disabled>{{ mainText }}</option>
		<option value="all">Tutti</option>
		<option
			v-for="(genere, index) in arrayTornatoPieno"
			:key="index"
			:value="index"
		>
			{{ genere }}
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
			arrayGeneri: []
		};
	},
	methods: {}
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
