<template>
        <button  @dblclick="deleteTodo($event)" class="wrapper" @click="completeTodo">
            <h1 class="title">{{ title }}</h1>
        </button>
</template>


<script>
    


    export default {
        props: ['id','title'],
        methods: {
            deleteTodo(event) {
                event.target.remove()
            },
            completeTodo() {
                if (event.target.className === 'wrapper') {
                    event.target.className = 'completeWrapper'
                } else if (event.target.className === 'completeWrapper') {
                    event.target.className = 'wrapper'
                }
            }
        }
    }
</script>


<style>
    .wrapper {
        padding: 30px 14px;
        background-color: red;
        border: 2px solid rgb(48, 48, 48);
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    .completeWrapper {
        padding: 30px 14px;
        background-color: rgb(45, 193, 0);
        border: 2px solid rgb(48, 48, 48);
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    .title {
        font-family: 'Montserrat', sans-serif;
        font-weight: 900;
        font-size: 26px;
        color: rgb(48, 48, 48);
    }
</style>