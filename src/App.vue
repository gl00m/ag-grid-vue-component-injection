<template>
  <div id="app">
    <ag-table
      :column-defs="columnDefs"
      :row-data="rowData"
    />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import AgTable from '@/components/AgTable.vue';

@Component({
  components: {
    AgTable,
  },
})
export default class App extends Vue {
  public columnDefs = [
    {field: 'name'},
    {field: 'color', type: 'icon'},
  ]
  public rowData = [
    {name: 'Alice', color: '#FF0000'},
    {name: 'Bob', color: '#0000FF'},
  ]
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 100%;
}
</style>
