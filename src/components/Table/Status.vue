<template>
  <span class="badge" :class="whichColor()">{{status}}</span>
</template>

<script>
  export default {
    name: 'Status',
    props: {
      status: String
    },
    methods: {
      whichColor () {
        if (this.status == 'failed') {
          return 'badge-danger'
        } else if (this.status == 'delayed') {
          return 'badge-warning'
        }
        return 'badge-info'
      }
    }
  }
</script>

<style scoped>
  
  .badge {
    width: 100px;
    text-transform: uppercase;
    padding: 7px 0;
    font-size: .88em;
    border-radius: 6px;
  }
</style>
