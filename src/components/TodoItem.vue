<template>
  <ul class="list-group">
    <li v-for="todo in allTodos" :key="todo.id" class="item_todo list-group-item">
      <div class="before_edit" v-if="!isEdit">
        <el-checkbox v-model="checked">{{ todo.title }}</el-checkbox>
        <div>
          <i class="el-icon-edit mr-2"></i>
          <i class="el-icon-delete" @click="deleteTodo(todo.id)"></i>
        </div>
      </div>
      <div v-else>
        <el-input placeholder="Please input" v-model="input_edit_todo">
          <el-button slot="append" icon="el-icon-finished"></el-button>
        </el-input>
      </div>
    </li>
  </ul>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "TodoItem",
  data: function() {
    return {
      checked: [],
      isEdit: false,
      input_edit_todo: ""
    };
  },
  created: function() {
    this.fetchTodos();
    console.log("this:", this);
  },
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo"])
  },
  computed: mapGetters(["allTodos"])
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.item_todo .before_edit {
  text-align: left;
  display: flex;
  justify-content: space-between;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
