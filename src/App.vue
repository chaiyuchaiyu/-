<template>
  
  <div id="root">
    <h1 class="titlePosition">备忘录</h1>
    
    <div class="todo-container">
      <div class="todo-wrap">
        <Header :addTodo="addTodo"/>
        <List 
          :todos="todos" 
          :changeCheck="changeCheck" 
          :Delete="Delete"
        />
        <Footer :todos="todos" :changeAll="changeAll" :cleanDone="cleanDone"/>
      </div>
    </div>
  </div>

</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import List from './components/List.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    List
  },
    data() {
    return {
      todos: [
      ]
    }
    },
  methods: {
    //加入事件
    addTodo(todo) {
      this.todos.unshift(todo)
    },
    changeCheck(id) {
      this.todos.forEach((todo) => {
        if(todo.id===id) todo.done=!todo.done
      })
    },
    Delete(id) {
      this.todos=this.todos.filter((todo) => {
        return todo.id!==id
      })
    },
    changeAll(done) {
      this.todos.forEach((todo) => { todo.done = done })
    },
    cleanDone() {
      this.todos=this.todos.filter((todo) => {
        return todo.done===false
      })
    }
  },

}
</script>

<style>
  /*base*/
  body {
    background: #fff;
  }
  .titlePosition{
    text-align: center;
  }

  .btn {
    display: inline-block;
    padding: 4px 12px;
    margin-bottom: 0;
    font-size: 14px;
    line-height: 20px;
    text-align: center;
    vertical-align: middle;
    cursor: pointer;
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 4px;
  }

  .btn-danger {
    color: #fff;
    background-color: #da4f49;
    border: 1px solid #bd362f;
  }

  .btn-danger:hover {
    color: #fff;
    background-color: #bd362f;
  }

  .btn:focus {
    outline: none;
  }

  .todo-container {
    width: 600px;
    margin: 0 auto;
  }
  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }








</style>
