<template>
  <div class="task-grid">
    <template v-if="tasks.length">
      <TaskApp class="task"  v-for="(task, i) in tasks" :key="task.name" 
      @taskDeleted="$emit('taskDeleted', i)"
      @taskStateChanged ="$emit('taskStateChanged',i)"
      :task="task" />
    </template>
    <p v-else class="no-task"  >Sua vida está em dia, por enquanto...</p>
  </div>
</template>
  
<script>
import TaskApp from "./TaskApp.vue";

export default {
  components: { TaskApp },
  props: {
    tasks: { type: Array, required: true },
  },
  mounted() {
    console.log(this.tasks); // Verifique se as tarefas estão chegando corretamente
  },
};
</script>

<style>
.task-grid {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  }

.task-grid .task {
  margin: 15px;

}

.no-task {
  color: #aaa;
  font-size: 1.7rem;
}
</style>