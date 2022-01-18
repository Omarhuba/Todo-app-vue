<template>
  <div class="todoItem">
      <span class="todoItem">
          <input type="checkbox" name="done" @click="$emit('toggle')">
        <p> 
            {{todos.content}} 
            {{todos.done}} 
        </p>
        <img src="../assets/delete.svg"  @click="$emit('removeTodo')" class="delete">
      </span>
  </div>
</template>')'

<script>
export default {
    props: ['todos']

}
</script>

<style scoped>
.todoItem {
    display: flex;
    justify-content: space-between;
    width: 350px;
    height: 50px;
    background-color: #ccc;
}

</style>