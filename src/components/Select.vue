<template>
	<select class="form-select">
		<option selected>{{ mainText }}</option>
		<option value="1">One</option>
		<option value="2">Two</option>
		<option value="3">Three</option>
	</select>
</template>

<script>
export default {
	name: "Select",
	props: {
		mainText: String
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
