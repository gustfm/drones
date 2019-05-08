<template>
  <div class="customer-content">
    <img :src="imgLink" class="img-thumbnail">
    <div class="customer-content-info">
      <p class="name">{{name}}</p>
      <p class="address">{{address}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Customer',
  props: {
    imgLink: String,
    name: String,
    address: String
  }
}
</script>

<style scoped>
  .customer-content {
    display: flex;
    justify-content: flex-start;
    align-items: center;

    width: auto;
    padding: 0 1px;
    margin-right: 0;
  }
  .customer-content-info {
    margin-left: 10px;
  }
  .name, .address {
    margin: 0;
  }
  .name {
    font-size: 1.8em;
    font-weight: bold;
    padding: 0;
  }
  .address {
    font-size: 0.9em;
    text-transform: uppercase;
    padding-left: 1px;
  }
</style>
