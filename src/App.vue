<template>
  <div>
    <button @click = "addLike">Like</button>
    <button @click = "addDisLike">DisLike</button>
    <div>
      Кол-во лайков <strong>{{ likes }}</strong>
    </div>
    <div>
      Кол-во дизлайков <strong>{{ dislikes }}</strong>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 0
    }
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDisLike() {
      this.dislikes += 1;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
