<template>
	<div>
		<ul class='list-unstyled'>
			<ListItem 
				v-for='item in listItems'
				:key='item.id'
				:text='item.text'
				:id='item.id'
				@delete-item='logEvent'
			></ListItem>
		</ul>
	</div>
</template>

<script>
import ListItem from "./ListItem.vue";
export default {
	props: ['listItems'],
	components: { ListItem },
	methods: {
		logEvent(e) {
			this.$emit("delete-item", e)
		}
	}

}
</script>

<style>

</style>