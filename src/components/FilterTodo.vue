<template>
  <div class="filter-todo">
    <el-select v-model="value" placeholder="Select" @change="filterTodos($event)">
      <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
    </el-select>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "FilterTodo",
  data() {
    return {
      options: [
        {
          value: "200",
          label: "200"
        },
        {
          value: "100",
          label: "100"
        },
        {
          value: "50",
          label: "50"
        },
        {
          value: "20",
          label: "20"
        },
        {
          value: "10",
          label: "10"
        }
      ],
      value: ""
    };
  },
  methods: mapActions(["filterTodos"]),
  created() {
    console.log("limit:", this);
  }
};
</script>

<style scoped>
.filter-todo {
  margin-bottom: 50px;
}
</style>