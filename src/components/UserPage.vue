<template>
  <ejs-appbar class="page-header">
    <div class="flex-container">
      <div class="menuDiv" >
          <font-awesome-icon :icon="['fas', (!showMenu ?'bars': 'xmark')]" class="menuicon" size="2x" @click="openMenu"/>
      </div>
      <div class="logoDiv">
        <img src="../assets/tplogo.png" alt="Cardinal" 
        style="height: 2rem;
            width: 12rem;
            margin-top: 10px;" />
      </div>
      <div class="iconMenuBox">
        <font-awesome-icon :icon="['fas', 'magnifying-glass']" class="iconMenu" @click="openSearch"/>
        <font-awesome-icon :icon="['far', 'heart']" class="iconMenu"/>
        <font-awesome-icon :icon="['fas', 'cart-shopping']" class="iconMenu"/>
        <font-awesome-icon :icon="['far', 'user']" class="iconMenu"/>
      </div>
    </div>
  </ejs-appbar>
  <el-drawer v-model="drawer" title="I am the title" size="300" :with-header="false">
    <search @onSearchClose="onSearchClose"/>
  </el-drawer>
  <div class="page-container">
      <div v-if="showMenu" :class="('menuContainer '+(showMenu ? 'open' : 'close'))">
        <menu-page />
      </div>
    <corousel/>
  </div>
</template>

<script>
import { AppBarComponent } from '@syncfusion/ej2-vue-navigations';
//import { ButtonComponent } from "@syncfusion/ej2-vue-buttons";
//import { SpeedDialComponent } from "@syncfusion/ej2-vue-buttons";
import corousel from './corousel.vue';
//import product from './product.vue'
//import pageFooter from './pageFooter.vue';
import searchBoxVue from '../formComponents/searchBox.vue';
import menuPage from './menuPage.vue';

export default {
  name: 'UserPage',
  components: {
    "ejs-appbar": AppBarComponent,
    'corousel': corousel,
    //'product': product,
   // 'pageFooter': pageFooter,
    'search': searchBoxVue,
    //'ejs-button': ButtonComponent,
    'menu-page': menuPage
  },
  data() {
  return {
    showMenu: false,
    showSearch: false,
    drawer: false,
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
},
methods: {
  openMenu() {
    this.showMenu = !this.showMenu
  },
  openSearch() {
   // this.showSearch = !this.showSearch
    this.drawer = true
  },
  onSearchClose() {
    this.drawer = false
  }
}
}
</script>


<style scoped>

.e-appbar {
    padding: 0px;
    box-shadow: none;
    background: transparent !important;
}

.page-header{
    height: 6vh;
    width: 100%;
    position: absolute;
    z-index: 1000;
    border: 0px !important;
}

.page-container {
    position: relative;
    width: 100%;
    height: 100vh;
}

.menuContainer {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 10;
  margin-top: 0%;
}

.menuContainer .open {
  animation: 1s slide-up;
}

.menuContainer .close {
  animation: 1s slide-down;
}

@keyframes slide-up {
  from {
    margin-top: 100%;
    height: 300%;
  }
  to {
    margin-top: 0%;
    height: 100%;
    /*background-color: hsl(208, 100%, 97%,0.7);*/
  }
}

@keyframes slide-down {
  from {
    margin-top: 0%;
    height: 100%;
    
  }
  to {
    margin-top: 100%;
    height: 300%;
    /*background-color: hsl(208, 100%, 97%,0.7);*/
  }
}


.flex-container {
  flex-direction: row;
  align-items: stretch !important;
  justify-content: space-between;
}

.menuDiv {
  padding-top:10px;
  order: 1;
  min-width: 45px;
}

.logoDiv {
  max-width: 250px;
  max-height: 100px;
  padding-left: 5rem;
  flex-shrink:0;
  order: 2;
}

.iconMenuBox {
  order: 3;
  padding-right: 1rem;
  padding-top: 0.55rem;
  position: relative;
}

.iconMenu {
  height: 22px;
  padding: 0px 15px 0px 0px;
  font-size: 4rem;
}


.menuicon{
  margin-left: 1rem;
  cursor: pointer;
}


@media (max-width: 635px) {
  .flex-container {
    flex-wrap: wrap;
  }
  .page-header{
      height: 13vh;
  }
  .logoDiv {
    max-width: 200px;
    max-height: 60px;
    padding-left: 1rem;
  }
  .iconMenuBox {
    order: 3;
    padding-left: 1rem;
  }

  .menuDiv {
    order: 2;
    padding-top:8px;
  }

  .menuicon{
    margin-right: 1rem;
  }
}



</style>
