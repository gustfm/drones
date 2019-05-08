<template>
  <div id="app">
    <div class="main">
      <InputValue @sendId="getById" @sendName="getByClientName" @sendStatus="getByStatus" />
      <Table :data="this.data" />
    </div>
  </div>
</template>

<script>
import Table from './components/Table/Table.vue'
import InputValue from './components/InputValue'

export default {
  name: 'app',
  components: {
    Table,
    InputValue
  },
  data () {
    return {
      baseUrl: 'http://services.solucx.com.br/mock/',
      data: [],
      auxData: []
    }
  },
  methods: {
    getById(id) {
      if (id == '') {
        this.data = this.auxData
      } else {
        this.data = this.data.filter((el, data) => {
          return el.id.toString().includes(id) ? el: ''
        })
      }
    },
    getByClientName(name) {
      if (name == '') {
        this.data = this.auxData
      } else {
        this.data = this.data.filter((el, data) => {
          return el.name.includes(name) ? el: ''
        })
      }
    },
    getByStatus(status) {
      if (status == '') {
        this.data = this.auxData
      } else {
        this.data = this.data.filter((el, data) => {
          return el.status.includes(status) ? el: ''
        })
      }
    },
    async getAllData() {
      const response = await this.$http.get(this.baseUrl+'drones')
      this.data = response.data
      this.auxData = response.data
    }
  },
  created () {
    this.getAllData()
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  width: 90vw;
  margin: 0 auto;

  display: flex;
}
.main {
  margin: 100px auto;
}
</style>
