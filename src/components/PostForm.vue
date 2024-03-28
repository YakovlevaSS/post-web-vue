<template>
    <form @submit.prevent>
        <h4>Создание поста</h4>
        <input v-model="post.title" class="input" type="text"
            placeholder="Название">
        <input v-model="post.body" class="input" type="text" placeholder="Описание">
        <button class="button" @click="createPost">Cоздать</button>
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
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    },
  }
}

</script>


<style>
form {
  display: flex;
  flex-direction: column;

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