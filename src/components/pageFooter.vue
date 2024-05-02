<template>
  <div class="control-container">
    <ejs-appbar position="Bottom" colorMode="Inherit" cssClass="footer-bar">
      
    </ejs-appbar>
  </div>
</template>

<script>
  import { AppBarComponent } from '@syncfusion/ej2-vue-navigations';

  export default {
    components: {
    "ejs-appbar": AppBarComponent,
  },
    data: function () {
      return {};
    }
  };
</script>

<style scoped>
  .control-container {
    height: 300px;
    background-color: #123027;
    margin: 0 auto;
    position: relative;
  }

  .footer-bar {
    height: 300px;
  }

  .control-container .e-btn.e-inherit {
    margin: 0 3px;
  }
</style>