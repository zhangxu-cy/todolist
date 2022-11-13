<template>
  <div id="MyList" class="MyList">
    <ul>
      <li>
        <MyItem v-for="todos in todos" :key="todos.index" :todos="todos" :cy_Delete="cy_Delete"/>
      </li>
    </ul>
  </div>
</template>

<script>
import MyItem from './MyItem.vue';


export default {
  name: 'MyList',
  props:['todos','cy_Delete'],
  components: {
    MyItem
  }
}
</script>

<style>
.MyList {
  width: 500px;
}
</style>
