<template>
  <div class="task-progress">
    <span class="progress-value">{{ progress }}%</span>
    <div class="progress-bar" :style="{width: progress + '%'}"></div>
  </div>
</template>

<script>
export default {
    props: {
        progress: { type: Number, deafault: 0}
    }
}
</script>

<style>
    .task-progress {
        position:relative ;
        width: 90%;
        border: 1px solid #fff;
        color: #fff;
        border-radius: 8px;
        margin-bottom: 15px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .progress-bar {
        position: absolute;
        border-radius: 8px;
        height: 100%;
        background-color: #4caf50;
        align-self: flex-start;
    }

    .progress-value {
        z-index: 1;
        
    }
</style>