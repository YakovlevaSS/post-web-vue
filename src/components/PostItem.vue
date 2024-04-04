<template>
    <div class="post">
        <div><strong>Название: </strong>{{ post.title }}</div>
        <div><strong>Описание: </strong>{{ post.body }}</div>
        <my-button style="" @click="createPost">
            Удалить
        </my-button>
    </div>

</template>


<script>
import MyButton from "@/components/UI/MyButton.vue"
export default {
    components: {
    MyButton
  },
    props: {
        post: {
            type: Object,
            required: true,
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
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>