<template>
  <div class="todoItems">
      <span class="todoItem">
          <input type="checkbox" name="done" @click="$emit('toggle')" class="checkBox">
        <p> 
            {{todos.content}} 
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

<style scoped lang="scss">
.todoItem {
    display: flex;
    justify-content: space-between;
    width: 350px;
    height: 50px;
    margin: 10px;
    background-color: #ccc;
    img{
        width: 30px;
        height: 30px;
        margin: 10px ;
    }
}
.checkBox{
    margin: 20px 0 0 20px;
}
</style>