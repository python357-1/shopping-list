<template>
	<div>
		<Header></Header>
		<List 
			v-bind:list-items='items'
			@delete-item='deleteItem'>
		</List>
		<AddItem
			@add-item='addItem'
		></AddItem>
		<Footer></Footer>
	</div>
</template>

<script>
import Header from "./components/Header.vue"
import List	  from "./components/List.vue"
import Footer from "./components/Footer.vue"
import AddItem from "./components/AddItem.vue"

import {v4 as uuidv4} from "uuid"

export default {
	components: { Header, Footer, List, AddItem },
	data () {
		return {
			items: [
				{
					text: "this is a test thing",
					id: uuidv4()
				},
				{
					text: "this is another thing",
					id: uuidv4()
				}
			]
		}
	},
	methods: {
		addItem(i) {
			let item = {
				text: i,
				id: uuidv4()
			}

			this.items.push(item)
		},
		deleteItem(i) {
			this.items = this.items.filter(e => {
				if (e.id != i) {
					return e
				}
			})
		}
	}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
