<template>
	<form>
		<h4>Создание поста</h4>
		<input
			type="text"
			placeholder="Название"
			class="input"
			v-model="post.title"
		/>
<!--			v-bind:value="post.title"-->
<!--			@input="post.title = $event.target.value"-->

		<input
			type="text"
			placeholder="Описание"
			class="input"
			v-model="post.body"
		/>
		<button
			class="btn"
			@click.prevent="createPost"
		>
			Создать
		</button>
	</form>
</template>

<script>
export default {
	data() {
		return {
			post: {
				title: '',
				body: '',
			}
		}
	},
	methods: {
		createPost() {
			this.post.id = Date.now();
			this.$emit('create', this.post);
			this.post = {
				title: '',
				body: '',
			}
		}
	}
}
</script>

<style scoped>
form {
	display: flex;
	flex-direction: column;
}

.input {
	width: 100%;
	border: 2px solid teal;
	padding: 10px 15px;
	margin-top: 15px;
}

.btn {
	align-self: flex-end;
	margin-top: 10px;
	padding: 10px 15px;
	background: none;
	color: teal;
	border: 2px solid teal;
}
</style>