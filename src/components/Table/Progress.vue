<template>
  <div class="progress" >
    <div :style="{width: battery+'%'}" class="progress-bar"
      role="progressbar"
      aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
  </div>
</template>

<script>
  export default {
    name: 'Progress',
    props: {
      battery: Number,
    }
  }
</script>

<style scoped>
  .progress {
    height: 4px;
  }
  .progress-bar {
    height: 10px;
    width: 10%;
  }
</style>
