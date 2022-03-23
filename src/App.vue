<template>
  <div id="app">
    <h1>Todo List</h1>
        <ol>
            <li v-for="todo in todos" :key="todo.id">
              {{ todo.text }} 
              <button class="buttonRemove" >Remove</button>
              <button class="buttonEdit" >Edit</button>
            </li>
        </ol>

        <input type="text" placeholder="Masukkan Todo List anda" v-model="newTodo" @keyup.enter="addTodo">

        <ButtonInput @tambahin="addTodo" />
        
        <div v-if="todos.length >= 4">Hebat!</div>
  </div>
</template>

<script>
import ButtonInput from '@/components/ButtonInput.vue'

export default {
  name: 'App',
  components: {
    ButtonInput
  },

  data () {
    return {
      newTodo: '',
      todos: []
    }
  },

  methods: {
    addTodo() {
      this.todos.push({ text: this.newTodo })
      this.newTodo = ''
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: rgb(99, 99, 99)
}

input {
  width: 80%;
  border: 2px solid #aaa;
  border-radius: 3px;
}

.buttonTambahkan {
  margin-right: 20px;
  margin-left: 50px;
}
</style>
