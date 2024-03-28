<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" />
  </div>
</template>

<script>
import PostForm from "./components/PostForm";
import PostList from "./components/PostList";

export default {
  components: {
    PostForm, PostList
  },
  data() {
    return {
      posts: [
        { id: 1, title: 'js', body: 'описание поста 1' },
        { id: 2, title: 'js 2', body: 'описание поста 2' },
        { id: 3, title: 'js 3', body: 'описание поста 3' },
      ],
      title: '',
      body: ''
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
