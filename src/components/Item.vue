<template>
        <li>
          <label>
            <input type="checkbox" :checked="transport.done" @click="changeCheck(transport.id)"/>
            <span>{{transport.title}}</span>
          </label>
          <button class="btn btn-danger" @click="Delete(transport.id)">删除</button>
        </li>
</template>

<script>
export default {
  name: 'ITEM',
  //声明接受tudo对象
  props: ['transport','changeCheck','Delete'],
  methods: {

  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /*item*/
  li {
    list-style: none;
    height: 36px;
    line-height: 36px;
    padding: 0 5px;
    border-bottom: 1px solid #e2d6d6;
  }

  li label {
    float: left;
    cursor: pointer;
  }

  li label li input {
    vertical-align: middle;
    margin-right: 6px;
    position: relative;
    top: -1px;
  }

  li button {
    float: right;
    display: none;
    margin-top: 3px;
  }

  li:before {
    content: initial;
  }

  li:last-child {
    border-bottom: none;
  }
  li:hover{
    background-color:#cac5c5
  }
   li:hover button{
    display:block
  }
</style>
