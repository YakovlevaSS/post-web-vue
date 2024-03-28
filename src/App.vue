<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input v-bind:value="title" @input="title = $event.target.value" class="input" type="text" placeholder="Название">
      <input v-bind:value="body" @input="body = $event.target.value" class="input" type="text" placeholder="Описание">
      <button class="button" @click="createPost">Cоздать</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
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
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      }
      this.posts.push(newPost);
      this.title = '';
      this.body = '';
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

form {
  display: flex;
  flex-direction: column;

}

.post {
  padding: 12px;
  border: 2px solid teal;
  border-radius: 6px;
  margin-top: 12px;
}

.input {
  width: 100%;
  border: 1px solid teal;
  margin-top: 12px;
  padding: 6px;
  border-radius: 6px;
}

.button {
  margin-top: 15px;
  align-self: flex-end;
  padding: 6px;
  background: none;
  color: teal;
  border: 1px solid teal;
  border-radius: 6px;
}
</style>
