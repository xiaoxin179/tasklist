<template>
  <div class="add">
    <div class="input-group mb-3">
      <input
        type="text"
        class="form-control"
        placeholder="请输入需要添加的任务"
        aria-label="Recipient's username"
        aria-describedby="basic-addon2"
        v-model="taskname"
      />
      <button class="btn-primary" @click="submit">提交</button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    name: "addtask";
    return {
      taskname: "",
    };
  },
  emits:["addTask"],
  methods: {
    submit() {
        this.$emit('addTask',this.taskname)
        this.taskname=""
    },
  },
};
</script>
<style scoped>
.add{
    width: 500px;
    margin: auto;
}
</style>