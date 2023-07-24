<template>
  <div class="taskbutton">
    <div class="btn-group" role="group" aria-label="Basic example">
      <button
        type="button"
        class="btn"
        :class="active === 0 ? 'btn-primary' : 'btn-secondary'"
        @click="changeActive(0)"
      >
        全部计划
      </button>
      <button
        type="button"
        class="btn"
        :class="active === 1 ? 'btn-primary' : 'btn-secondary'"
        @click="changeActive(0)"
      >
        完成计划
      </button>
      <button
        type="button"
        class="btn"
        :class="active === 2 ? 'btn-primary' : 'btn-secondary'"
        @click="changeActive(0)"
      >
        未完成计划
      </button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      namne: "TaskButton",
      active: 0,
    };
  },
  methods:{
    changeActive(index){
        this.active=index;
        // <!-- emit的作用是触发自定义事件，携带事件名，并且传递参数 -->
        this.$emit('changeActive',index);
    }

  }
};
</script>
<style scoped>
.btn-group {
  width: 500px;
}
</style>