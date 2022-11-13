<template>
  <div id="MyHeader" class="header">
    <input type="text" @keyup.enter="add" >
  </div>
</template> 

<script>


export default {
  name: 'MyHeader',
  props:['addTodoList'],
  methods:{
    add(a){
      const obj = {id:'004',name:a.target.value,check:false};
      this.addTodoList(obj)
    }
  },
}
</script>

<style scoped>
.header input{
    width: 400px;
    height: 30px;
    margin-top: 30px;
}
</style>
