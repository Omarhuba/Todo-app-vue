<template>
  <div class="todoList">
      <TodoItem v-for="item in todos" :key="item.id" :todos="item"
    @removeTodo="$emit('removeTodo', item)"
    @toggle="$emit('toggle', item)"
       />
  </div>
</template>

<script>
import TodoItem from "./todoItem.vue"
export default {
    components: {
        TodoItem,
    },
    props: ['todos'],

}
</script>

<style scoped>
.todoList{
    margin: 10px;
}

</style>