<template>
  <ul class="todo-main">
    <Item 
      v-for="todo in todos" 
      :key='todo.id' 
      :transport="todo" 
      :changeCheck="changeCheck"
      :Delete="Delete"
    />
  </ul>
</template>

<script>
import Item from './Item.vue'
export default {
  name: 'LIST',
  components: {
    Item
  },
  props:['todos','changeCheck','Delete']

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /*list*/
  .todo-main {
    margin-left: 0px;
    border: 1px solid #dbd0d0;
    border-radius: 20px;
    padding: 0px;
  }

  .todo-empty {
    height: 40px;
    line-height: 40px;
    border: 1px solid #ebdfdf;
    border-radius: 2px;
    padding-left: 5px;
    margin-top: 10px;
  }

</style>
