<template>
	<p>Counter: {{ counter }}</p>
</template>

<script>
	export default {
		computed: {
			counter() {
				return this.$store.getters.computedCounter
			}
		}
	}
</script>

<style>

</style>

