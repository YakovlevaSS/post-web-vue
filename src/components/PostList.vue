<template>
    <div class="post" v-for="post in posts">
        <div><strong>Название: </strong>{{ post.title }}</div>
        <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
</template>


<script>
export default {
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>


<style>
.post {
    padding: 12px;
    border: 2px solid teal;
    border-radius: 6px;
    margin-top: 12px;
}
</style>