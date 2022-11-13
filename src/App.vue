<template>
  <div id="app">
    <div class="app_center">
      <MyHeader :addTodoList="addTodoList"/>
      <MyList :todos="todos" :cy_Delete="cy_Delete"/>
      <MyFooter :nb="nbs" :todo="todos" :cy_cleans="cy_cleans"/>
    </div> 
  </div>
</template>

<script>
import MyHeader from './components/MyHeader';
import MyList from './components/MyList';
import MyFooter from './components/MyFooter';

export default {
  name: 'App',
  data() {
    return {
      todos: [
        { id: '001', name: '吃饭', check: true },
        { id: '002', name: '睡觉', check: false },
        { id: '003', name: '打架', check: true },
        { id: '002', name: '篮球', check: false },
        { id: '003', name: '看书', check: true }
      ],
      nbs:'清除已经完成的事'
    }
  },
  methods: {
    // 添加一个todo
    addTodoList(x) {
      this.todos.push(x);
    },
    // 选择或取消选择一个
    checkTodo(id){
      this.todos.forEach((todo) =>{
        if(todo.id === id) todo.done = !todo.done;
      })
    },
    cy_Delete(id){
      this.todos = this.todos.filter((todo)=>{
        return todo.id !== id;
      })
    },
    cy_check(){
      // const new_todos =[];
      for(var i=0;i<this.todos.length;i++){
        console.log(this.todos[i]);
      }
    },
    cy_cleans(){
      var cy=[];
      for( var j =0; j<this.todos.length;j++){
        if(this.todos[j].check == false){
          cy.push(this.todos[j]);
        }
      }
      this.todos = cy;
    }
  },
  components: {
    MyHeader,
    MyList,
    MyFooter,
  }
}
</script>

<style>
#app {
  width: 100%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.app_center {
  width: 600px;
  margin: 0 auto;
  height: 400px;
  background-color: #f6f6f6;
}
</style>
