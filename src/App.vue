<template>
  <div>
    <h1>任务清单</h1>
    <!-- 字符组件之间的传值 -->
    <TaskList :tasklist="tasklist"></TaskList>
    <TodoButton/>
  </div>
</template>

<script>
import TaskList from './components/TaskList.vue'
import TodoButton from './components/TodoButton.vue'
export default {
  name: "App",
  components: {
    TaskList,
    TodoButton
  },
  data(){
      return{
        tasklist:[
          {id:1,task:'吃饭',isCompleted:true},
          {id:2,task:'吃饭',isCompleted:true},
          {id:3,task:'吃饭',isCompleted:false}
        ]
      }
    }
};
</script>
