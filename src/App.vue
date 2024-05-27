<template>
  <user-page />
</template>

<script>
import UserPageVue from './components/UserPage.vue'

export default {
  name: 'App',
  components: {
    'user-page': UserPageVue
  }
}
</script>


<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-calendars/styles/material.css";
@import "../node_modules/@syncfusion/ej2-dropdowns/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
@import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
@import "../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-grids/styles/material.css";
@import '../node_modules/@syncfusion/ej2-layouts/styles/material.css';
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-family: "Urbanist", sans-serif !important;
  font-optical-sizing: auto;
  font-style: normal;
  overflow: hidden;
}

.e-control {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  font-family: "Urbanist", sans-serif !important;
  font-optical-sizing: auto;
  font-style: normal;
}

.el-drawer__body{
  padding: 5px !important;
}

.buttons {
  background-color: #020202 !important;
}

body {
  margin: 0px;
}
</style>
