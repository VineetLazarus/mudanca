<template>
  <div class="app-div">
    <ejs-appbar colorMode="Inherit" cssClass="app-bar">
      <div class="flex-container">
        <div class="logoDiv"><img src="../assets/tlogo.png" alt="Cardinal" style="height: 100%; width: 100%" /></div>
        <div class="searchBox"><search /></div>
        <div class="menuButton">
          <font-awesome-icon :icon="['fas', 'bars']" class="menuicon"/>
          <ejs-button isPrimary="true" cssClass="buttons">
            <font-awesome-icon :icon="['far', 'user']" />
            Login
          </ejs-button>
        </div>
      </div>
    </ejs-appbar>
  </div>
  <div class="page-container">
    <el-scrollbar height="800px">
        <corousel />
       <!-- <product />
        <pageFooter />-->
    </el-scrollbar>
  </div>
</template>

<script>
import { AppBarComponent } from '@syncfusion/ej2-vue-navigations';
import { ButtonComponent } from "@syncfusion/ej2-vue-buttons";
//import { SpeedDialComponent } from "@syncfusion/ej2-vue-buttons";
import corousel from './corousel.vue';
//import product from './product.vue'
//import pageFooter from './pageFooter.vue';
import searchBoxVue from '../formComponents/searchBox.vue';

export default {
  name: 'UserPage',
  components: {
    "ejs-appbar": AppBarComponent,
    'corousel': corousel,
    //'product': product,
   // 'pageFooter': pageFooter,
    'search': searchBoxVue,
     'ejs-button': ButtonComponent
  },
  data() {
  return {
     items: [
                {
                    title: 'Cut',
                    iconCss: 'speeddial-icons speeddial-icon-cut'
                },
                {
                    title: 'Copy',
                    iconCss: 'speeddial-icons speeddial-icon-copy'
                },
                {
                    title: 'Paste',
                    iconCss: 'speeddial-icons speeddial-icon-paste'
                },
                {
                    title: 'Delete',
                    iconCss: 'speeddial-icons speeddial-icon-delete'
                }
            ],
            radialSetting: { offset: '70px' },
            radialSetting1: { offset: '110px' }
  };
}
}
</script>


<style scoped>

.app-div {
    position: fixed;
    width: 100%;
    z-index: 1000;
}

.app-bar {
    height: 80px !important;
    width: 100%;
    position: relative;
    border: 0px !important;
}

.page-container {
    position: fixed;
    width: 100%;
    top: 80px;
    height: auto;
    overflow-y: scroll;
}

.flex-container {
  flex-direction: row;
  align-items: stretch !important;
  justify-content: space-between;
}

.logoDiv {
  max-width: 250px;
  max-height: 100px;
  flex-shrink:0;
  order: 1;
}

.searchBox {
  order: 2;
}

.menuButton {
  padding-top:15px;
  order: 3;
}

@media (max-width: 635px) {
  .flex-container {
    flex-wrap: wrap;
  }
  .app-bar {
    height: 120px !important;
  }
  .page-container {
    top: 120px;
  }
  .logoDiv {
    max-width: 200px;
    max-height: 60px;
  }
  .searchBox {
    order: 3;
  }

  .menuButton {
    order: 2;
  }
}

.menuicon{
  margin-right: 10px;
}



</style>
