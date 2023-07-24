<template>
  <div>
    <div class="list">
      <ul class="list-group">
        <li
          class="list-group-item d-flex justify-content-between align-items-center"
          v-for="item in tasklist" :key="item.id"
        >
        <!-- 复选框 -->
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              value=""
              :id="item.id"
              v-model="item.isCompleted"
            />
            <!-- 动态绑定css属性 -->
            <label class="form-check-label" :for="item.id" :class="item.isCompleted?'del':''">
              {{item.task}}
            </label>
        </div> 
          <span class="badge badge-primary badge-pill" v-if="item.isCompleted">已完成</span>
          <span class="badge badge-warning badge-pill" v-else>未完成</span>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
    props: {
    tasklist: {
      type: Array, 
      required: true
    }
  },
  data() {
    return {
      name: "TaskList",
    };
  },
};
</script>
<style scoped>
.list-group {
  width: 500px;
  margin: 20px auto;
}
.del{
    text-decoration: line-through;
}
</style>
