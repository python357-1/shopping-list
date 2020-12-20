<template>
	<div v-if='!adding'>
		<button
			@click='startAdd'>
			Add
		</button>
	</div>
	<div v-if='adding'>
		<form @submit='addItem'>
			<input type='text'/>
			<br>
			<input 
				type='submit'
				value='Add Item'
				id='submit-button'/>
		</form>
	</div>
</template>

<script>
export default {
	data() {
		return {
			adding: false
		}
	},
	emits: ['add-item'],
	methods: {
		addItem(e) {
			this.$emit("add-item", e.srcElement[0].value)
			this.adding = false;
		},
		startAdd() {
			this.adding = true;
		}
	}
}
</script>

<style scoped>
	button {
		background: #123;
		color: white;
		font-weight: 800;
		padding: 3px 10px;
		border-radius: 13px;
		border: 0;
	}

	#submit-button {
		height: 27px;
		padding: 1;
	}
</style>