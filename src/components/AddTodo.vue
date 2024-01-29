<template>
    <div class="block">
        <input class="inp" @keydown="addTodo" type="text" placeholder="Введите значение">
    </div>
</template>


<script>
    export default {
        methods: {
            addTodo () {
                this.$emit('addTodo', event)
            }
        }
    }
</script>


<style>
    .inp {
        padding: 12px 24px;
        border: 1px solid rgb(185, 185, 185);
        border-radius: 12px;
        text-align: left;
    }
    .block {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
</style>