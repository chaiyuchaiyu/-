<template>
  <div class="todo-footer" v-show="todos.length">
    <label>
      <input type="checkbox" :checked="(doneNum===todos.length)" @click="checkAll"/>
    </label>
    <span>
      <span>已完成{{doneNum}}</span> / 全部{{todos.length}}
    </span>
    <button class="btn btn-danger" @click="cleanDone">清除已完成任务</button>
  </div>
</template>

<script>
export default {
  name: 'FOOTER',
  props: ['todos','changeAll','cleanDone'],
  computed: {
    doneNum() {
      let i = 0;
      this.todos.forEach((todo) => {
        if (todo.done === true) i++;
      })
      return i
    }
  },
  methods: {
    checkAll(event) {
      this.changeAll(event.target.checked)
    }

  }
}
    
  
  
  
  


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /*footer*/
  .todo-footer {
    height: 40px;
    line-height: 40px;
    padding-left: 6px;
    margin-top: 5px;
  }

  .todo-footer label {
    display: inline-block;
    margin-right: 20px;
    cursor: pointer;
  }

  .todo-footer label input {
    position: relative;
    top: -1px;
    vertical-align: middle;
    margin-right: 5px;
  }

  .todo-footer button {
    float: right;
    margin-top: 5px;
  }

</style>
