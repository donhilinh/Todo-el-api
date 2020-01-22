<template>
  <div id="app">
    <h3>Todo Vue.js App</h3>
    <ul class="list-group">
      <TodoItem
        v-for="(data,index) in list_item"
        :key="index"
        :data="data"
        :index="index"
        @removeTodo="removeTodo"
        @editTodo="editTodo"
      />
    </ul>
    <el-input placeholder="Please input" v-model="input_todo">
      <template slot="append">
        <el-button type="primary" @click="addTodo">Add Todo</el-button>
      </template>
    </el-input>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem.vue";

export default {
  name: "app",
  components: {
    TodoItem
  },
  data: function() {
    return {
      list_item: [{ name: "item1" }, { name: "item2" }, { name: "item3" }],
      input_todo: ""
    };
  },
  methods: {
    addTodo: function() {
      this.list_item.push({
        name: this.input_todo
      });
      this.input_todo = "";
    },
    removeTodo: function(index) {
      this.list_item.splice(index, 1);
    },
    editTodo:function(data, index){
      this.list_item.splice(index,1,{name: data})
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 50%;
}
</style>
