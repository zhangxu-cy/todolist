<template>
  <div id="MyItem" class="MyItem">
    <input type="checkbox" name="" id="" :checked="todos.check" @click="handCheck(todos.id)" >
    <span>{{todos.name}}</span>
    <button class="cy_sc" @click="cy_shanchu(todos.id)">删除</button>
  </div>
</template>

<script>


export default {
  name: 'MyItem',
  // 子组件接收父组件的todos
  props:['todos','cy_Delete'],
  methods:{
    handCheck(id){
      console.log(id);
      // 通知app将checked取反  
    },
    cy_shanchu(id){
      this.cy_Delete(id);
    }
    
  }
}
</script>

<style>
.MyItem{
    height: 50px;
}
.MyItem:hover{
    background-color: #f6f6f6;
}
.MyItem:hover .cy_sc{
  display: block;
}
li{
  list-style: none;
}
.cy_sc{
  display: none;
  float: right;
  cursor: pointer;
}

</style>
