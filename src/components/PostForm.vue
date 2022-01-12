<template>
	<form>
		<h4>Создание поста</h4>
		<my-input
			type="text"
			placeholder="Название"
      v-model="post.title"
    />
<!--  v-model:value='post.title'  -->
		<my-input
			type="text"
			placeholder="Описание"
			v-model="post.body"
		/>
		<my-button
      style='margin-top:  15px'
			@click.prevent="createPost"
		>
			Создать
		</my-button>
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
</style>