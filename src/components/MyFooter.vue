<template>
  <div id="footer" class="footer">
   <span>{{doneTall()}}/{{todo.length}}</span>
   <span >已完成/任务总数</span>
   <button @click="cy_cleans()" class="clean" >{{nb}}</button>
  </div>
</template>

<script>


export default {
  props:['nb','todo','cy_cleans'],
  name: 'MyHeader',
  methods:{
    doneTall(){
      var zx =[];
      for(var i = 0; i<this.todo.length;i++){
        if(this.todo[i].check == true){
          zx.push(this.todo[i])
        }
      }
      return zx.length
    },
  }
}
</script>

<style>
.footer{
 font-size: 18px;
}
.clean{
  background-color: red;
  width: 200px;
  height: 40px;
  margin-left: 30px;
  cursor: pointer;
}
</style>
