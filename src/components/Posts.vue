<template>
  <main v-for="post in posts" :key="post.id" class="post_container">
    <h2>{{ post.title }}</h2>
    <p>{{ post.description }}</p>
  </main>
</template>

<script>
export default {
  props: ['posts'],
  data() {
    return {};
  },
};
</script>

<style scoped>
.post_container {
  margin-bottom: 20px;
}
</style>
