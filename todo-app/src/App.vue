<template>
<div class="app">

  <div id="todo">
    <header>
      <img src="./assets/teflon-panna.svg" alt="foto">
      <h1>TEFLON</h1>
      <h3>När det inte fasnar</h3>
    </header>
    <main>

    <TodoList :todos="todos" @removeTodo="removeTodo" /> 
    </main>
    <footer>
      <div class="footer">
        <input id="inputBox" 
        type="text" placeholder="Type your Todo here" 
        v-model="inputVal" 
        >
        <button @click="pushInput(inputVal)">Add Todo</button>
      </div>
    </footer>


  </div>
</div>
</template>

<script>
import TodoList from "./components/TodoList.vue"
export default {
 components: {
   TodoList,
 },
  data(){
    return {
      todos: [
        {
          id: 1, content: 'Köp bananpaj', done: 'false',
        },
        {
          id: 2, content: 'Köp bananpaj', done: 'false',
        },
        {
          id: 3, content: 'Köp bananpaj', done: 'false',
        },
        {
          id: 4, content: 'Köp grillkorv', done: 'false',
        }
      ],
      inputVal: '',
  
    }
  },
  methods: {
    pushInput(inputVal) {
        console.log(inputVal)
        console.log(this.todos.length)
        let todoid = this.todos.length + 1;
        let newTodo = {id: todoid, content: this.inputVal, done: false}
        this.todos.push(newTodo)
        this.inputVal = ''
    },
    removeTodo(item) {
      console.log(this.todos.id)
      this.todos = this.todos.filter(t => t.id != item.id)

    }


  }

}
</script>

<style scoped lang="scss">

.app{
  display:flex;
  align-items:center
}
#todo{
  display: flex;
  /* justify-content: center; */
  align-items: center;
  flex-direction: column;
  margin-top: 200px;
  padding: 2rem;
  width: 400px;
  height: 600px;
  border: 2px solid black;
}
.footer{
  display: flex;
  flex-direction: column;
  width: 350px;
  height: 50px;
  input{
    font-size: 1.1rem;
    
  }
  button{
    font-size: 1.1rem;
  }

}
</style>