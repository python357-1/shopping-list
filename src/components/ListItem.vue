<template>
	<li>
		<p class='h3'> {{text}} </p>
		<button @click='$emit("delete-item", id)'>X</button>
	</li>
</template>

<script>
export default {
	props: ['text', 'id'],
	emits: ['delete-item'],
}
</script>

<style scoped>
	p {
		text-decoration: underline;
		display: inline-block;
	}

	button {
		display: inline-block;
		margin: 0 10px;
		background-color: red;
		border-radius: 30px;
		border: 2px solid #123;
		color: white;
		padding: 2px 6px;
	}
</style>