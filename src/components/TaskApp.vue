<template>
  <div @click="$emit('taskStateChanged', task)"
    class="task-app" :class="stateClass">
    <span @click.stop="$emit('taskDeleted',task)" class="close">x</span>
    <p>{{ task.name }}</p>
  </div>
</template>

<script>
export default {
  props: {
    task: { type: Object, required: true },
  },
  computed: {
    stateClass() {
      return {
        pending: this.task.pending,
        done: !this.task.pending,
      };
    },
  },
};
</script>

<style>
.task-app {
  position: relative;
  box-sizing: border-box;
  height: 100px;
  width: 200px;
  padding: 10px;
  border-radius: 5px;
  font-size: 1.5rem;
  font-weight: 400;
  cursor: pointer;
  user-select: none;
  display: flex;
  justify-content: center;
  align-items: center;
}

.pending {
    border-left: 12px solid #b73229;
    color: #ddd;
    background-color: #f44336;
    font-size: 1.75rem;
    text-align: center;
}

.done {
    color: #ddd;
    border-left: 12px solid #0a8f08;
    background-color: #4caf50;
    text-decoration: line-through;
     font-size: 1.75rem;
    text-align: center;
}

.pending .close {
  background-color: #B73229;
}

.done .close {
  background-color:#0a8f08 ;
}

.close {
  position: absolute;
  right: 10px;
  top: 10px;
  font-size:0.9rem ;
  font-weight: 600;
  height: 20px;
  width: 20px;
  border-radius: 10px;
  display: flex;
  justify-content: center;
}
</style>