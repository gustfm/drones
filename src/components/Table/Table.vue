<template>
  <div class="table-responsive-sm">
    <table class="table table-sm">
      <thead>
        <tr>
          <th scope="col">DRONE</th>
          <th scope="col">CUSTOMER</th>
          <th scope="col">BATTERIES</th>
          <th scope="col">MAX SPEED</th>
          <th scope="col">AVERAGE SPEED</th>
          <th scope="col">STATUS</th>
        </tr>
      </thead>
      <tbody >
        <tr v-for="item in data" :key="item.id">
          <th class="item" id="key" scope="row">{{item.id}}</th>
          <td>
            <Customer
              :imgLink="item.image"
              :name="item.name"
              :address="item.address" />
          </td>
          <td class="item">
            <Progress :battery=item.battery />
          </td>
          <td class="item h-adjusting">
            <Speed :speed="item.max_speed" />
          </td>
          <td class="item h-adjusting">
            <Speed :speed="item.average_speed" />
          </td>
          <td class="item">
            <Status :status="item.status" />
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  import Customer from './Customer'
  import Progress from './Progress'
  import Speed from './Speed'
  import Status from './Status'

  export default {
    name: 'Table',
    components: {
      Customer,
      Progress,
      Speed,
      Status
    },
    props: {
      data: {}
    }
  }
</script>

<style scoped>
  table {
    display: inline-block;
    color: #59a6db;
  }
  .item {
    vertical-align: middle;
  }
  .h-adjusting {
    text-align: left;
    padding-left: 20px;
  }
  .table th {
    font-size: .85em;
    padding-right: 30px;
  }
  .table td {
    font-size: .8em;
    padding-right: 20px;
  }
</style>