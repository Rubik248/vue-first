<template>
    <div class="list">
        <todo-item 
            v-for="elem in items"
            :key="elem.id"
            :id="elem.id"
            :title="elem.title"
            @deleteTodo="deleteTodo"
        >
        </todo-item>
    </div>
</template>


<script>
import TodoItem from './TodoItem.vue';





export default {
    props: ['id', 'title', 'items'],
    components: {TodoItem}
}
</script>


<style>
    .list {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 30px;
        margin-top: 50px;
    }
</style>