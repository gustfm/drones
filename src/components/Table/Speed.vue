<template>
  <p>{{integer}}<span>{{decimal}} m/h</span></p>
</template>

<script>
  export default {
    name: 'Speed',
    props: {
      speed: 0
    },
    data () {
      return {
        integer: '0',
        decimal: '.0'
      }
    },
    methods: {
      transformNumber (speed) {
        if (speed != undefined) {
          speed = speed.toString()
          let splitedNumber = speed.split('.')
          this.integer = splitedNumber[0]
          splitedNumber[1] ? this.decimal = '.'+splitedNumber[1]: '.0'
        }
      }
    },
    created () {
      this.transformNumber(this.speed)
    }
  }
</script>

<style scoped>
  p {
    margin: 0;
    font-size: 1.5em;
  }
  span {
    font-size: 0.7em;
  }
</style>
