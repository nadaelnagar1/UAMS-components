<template>
   <AllTabs></AllTabs>
   
  <!-- <h3>Tabber</h3>
  <TabberComponent></TabberComponent>
  <h3>DataTable</h3>
  <DataTable></DataTable> -->
 
  
</template>

<script>
// import NestedExample from "./components/NestedExample.vue";
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";
// import root from "./root.json"
// import clinics from "./clinics.json" 
import "bootstrap-icons/font/bootstrap-icons.css";
// import TabberComponent from "./components/TabberComponent.vue";
// import DataTable from "./components/DataTable.vue";
import 'vue-good-table-next/dist/vue-good-table-next.css'
import AllTabs from "./components/AllInTabs.vue"


export default {
  data() {
    return {
      // clinicsData:clinics,
      // rootData:root,

    };
  },



  name: "App",
  components: {
    // NestedExample,
    // TabberComponent,
    // DataTable,
    AllTabs,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
