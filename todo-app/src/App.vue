<template>
<div class="app">

  <div id="todo">
    <header>
      <img src="./assets/teflon-panna.svg" alt="foto">
      <h1>TEFLON</h1>
      <h3>När det inte fasnar</h3>
    </header>
    <main>

    <TodoList :todos="todos" @removeTodo="removeTodo" @toggle="toggleDone"/> 
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
          id: 1, content: 'Köp bananpaj', done: false,
        },
        {
          id: 2, content: 'Köp bananpaj', done: false,
        },
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

    },
    toggleDone(item) {
      console.log(item)
      if(item.done == false) {
        return item.done = true;
      }else {
        return item.done = false
      }
    }


  }

}
</script>

<style lang="scss">
body{
  background-color: #eee
}
.app{
  display:flex;
  justify-content: center;
  align-items:center;
}
#todo{
  display: flex;
  justify-content: center; 
  align-items: center;
  flex-direction: column;
  margin-top: 100px;
  padding: 2rem;
  width: 350px;
  height: 500px;
  border: 2px solid black;
  background-color: #fff;
}
.footer{
  display: flex;
  flex-direction: column;
  width: 350px;
  height: 50px;
  input{
    font-size: 1.1rem;
    text-align: center;
    padding: 0.7rem;
    
  }
  button{
    font-size: 1.1rem;
    padding: 0.7rem;
    background-color: cadetblue;
    font-weight: 800;
    color: #fff
  }

}
</style>