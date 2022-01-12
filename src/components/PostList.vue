<template>
	<div v-if="posts.length">
    <transition-group name='post-list'>
      <post-item
        v-for="post in posts"
        :post="post"
        :key="post.id"
        @remove="$emit('remove', post)"
      />
    </transition-group>
	</div>
  <h2
    v-else
    style='color: red; margin-top: 20px; text-align: center'
  >
    Список постов пуст!
  </h2>

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

.post-list-item {
  display: inline-block;
  margin-right: 10px;
}
.post-list-enter-active,
.post-list-leave-active {
  transition: all 0.4s ease;
}
.post-list-enter-from,
.post-list-leave-to {
  opacity: 0;
  transform: translateX(100px);
}

/* для сортировки */
.post-list-move {
  transition: transform .5s ease;
}
</style>