<template lang="pug">
	.todo-input
		input(type="text", v-model="todo.name" @keydown.enter="addTodo").input
</template>

<script>
	let uniqId = 1;
	export default{
		data(){
			return{
				todo:{
					id: 0,
					name: '',
					checked: false	
				}
			}
		},
		methods:{
			addTodo(){
				this.todo.id = uniqId++;
				this.$emit('addTodo', {...this.todo});
				this.todo.name= "";
			}
		}
	}
</script>

<style lang="scss" src="styles/todoInput.scss"></style>