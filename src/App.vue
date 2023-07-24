<template>
  <div class="app">
    <h1>任务清单</h1>
    <AddTask @addTask="addTask"/>
    <!-- 字符组件之间的传值 -->
    <TaskList :tasklist="tasklist"></TaskList>
    <TodoButton @changeActive="changeActive"/>
  </div>
</template>

<script>
import TaskList from './components/TaskList.vue'
import TodoButton from './components/TodoButton.vue'
import AddTask from './components/AddTask.vue'
export default {
  name: "App",
  data(){
      return{
        active:0,
        tasklist:[
          {id:1,task:'吃饭',isCompleted:true},
          {id:2,task:'洗衣服',isCompleted:true},
          {id:3,task:'玩手机',isCompleted:false}
        ]
      }
    },
    // 计算属性，响应式式数据计算之后返回新的值,就是计算之后让todolist为新的值，通过这个来实现过滤的效果
  computed:{
    tasklist(){
      if(this.active === 0){
        return this.tasklist
      }else if(this.active === 1){
        return this.tasklist.filter(item =>item.isCompleted)
      }else{
        return this.tasklist.filter(item =>!item.isCompleted)
      }
    }
  },
  components: {
    TaskList,
    TodoButton,
    AddTask
  },
  methods:{
    changeActive(active){
      this.active=active
      // 测试值是否传递过来
      // console.log(this.active);
    },
    addTask(taskname){
      this.tasklist.push({
        id:this.tasklist.length+1,
        task:taskname,
        isCompleted:false
      })
    }
  },
};
</script>
