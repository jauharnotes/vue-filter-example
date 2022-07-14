<script>
import Filters from './components/Filters.vue';
import Posts from './components/Posts.vue';
import MOCK_DATA from './MOCK_DATA.json';

export default {
  data() {
    return {
      posts: MOCK_DATA,
      data: '',
    };
  },
  components: { Posts, Filters },
  methods: {
    filterPost(catName) {
      this.resetPost();
      if (catName != 'ALL') {
        this.posts = this.posts.filter((post) => {
          return post.category === catName;
        });
      }
    },
    search(term) {
      this.resetPost();
      this.posts = this.posts.filter((post) => {
        return post.title.toLowerCase().includes(term.toLowerCase());
      });
    },
    getData() {
      return this.data;
    },
    resetPost() {
      return (this.posts = MOCK_DATA);
    },
  },
};
</script>

<template>
  <main class="container">
    <div class="filter">
      <Filters :filterPost="filterPost" :search="search" />
    </div>
    <div class="post">
      <Posts :posts="posts" />
    </div>
  </main>
</template>

<style scoped>
.container {
  display: flex;
}

.filter {
  flex: 1;
}

.post {
  flex: 2;
}
</style>
