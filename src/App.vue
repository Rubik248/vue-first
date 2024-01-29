<template>
  <add-todo 
    @addTodo="addTodo"
    >
  </add-todo>
  <todo-list 
    :items="items"
    >
  </todo-list>
</template>


<script>
import AddTodo from './components/AddTodo.vue'
import TodoList from './components/TodoList.vue';



export default {
  components: {AddTodo, TodoList},
  data () {
        return {
            items: [
            {id: 1, title: 'Почистить зубы'},
            {id: 2, title: 'Заправить кровать'},
            {id: 3, title: 'Выкинуть мусор'}
        ]
        }
    },
  methods: {
    addTodo (event) {
      if (event.key === 'Enter') {
        let newItem = {
        id: Math.ceil(Math.random() * 99),
        title: event.target.value
        }
        this.items.push(newItem)
      } else {
        return this.items
      }
    },
    completeTodo (event) {
      
    }
  }
}

</script>


<style>
  * {
    margin: 0;
    padding: 0;
  }
  body {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-top: 50px;
  }
</style>
