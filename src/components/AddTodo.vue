<template>
  <div class="add-todo">
    <el-input placeholder="Please input" v-model="input_todo">
      <template slot="append">
        <el-button type="primary" @click="onClick">Add Todo</el-button>
      </template>
    </el-input>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      input_todo: ""
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onClick(e) {
      e.preventDefault();
      this.addTodo(this.input_todo);
    }
  }
};
</script>

<style scoped>
.add-todo {
  margin-bottom: 20px;
}
</style>