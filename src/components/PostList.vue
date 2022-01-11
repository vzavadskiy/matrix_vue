<template>
	<div>
		<h3>Список Пользователей</h3>
		<post-item
			v-for="post in posts"
			:post="post"
		/>

	</div>

</template>

<script>
import PostItem from "@/components/PostItem";
export default {
	components: {PostItem},
	props: {
		posts: {
			type: Array,
			require: true,
		}
	}
}
</script>

<style scoped>
.post {
	padding: 15px;
	border: 2px solid teal;
	margin-top: 15px;
	display: flex;
	align-items: center;
}
</style>