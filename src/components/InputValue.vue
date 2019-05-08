<template>
  <div class="container mb-3">
    <div class="row">
      <div class="col-sm">
        <div class="input-group mb-3">
          <input @input="sendId" type="text" class="form-control" placeholder="Id do drone">
        </div>
      </div>
      <div class="col-sm">
        <div class="input-group mb-3">
          <input @input="sendName" type="text" class="form-control" placeholder="Nome do cliente">
        </div>
      </div>
      <div class="col-sm">
        <div class="input-group mb-3">
          <input @input="sendStatus" type="text" class="form-control" placeholder="Status do drone">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'InputValue',
    methods: {
      sendId(event) {
        this.$emit('sendId', event.target.value)
      },
      sendName(event) {
        this.$emit('sendName', event.target.value.toLowerCase())
      },
      sendStatus() {
        this.$emit('sendStatus', event.target.value.toLowerCase())
      }
    }
  }
</script>

<style scoped></style>
