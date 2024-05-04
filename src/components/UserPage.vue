<template>
  <ejs-appbar class="page-header">
    <div class="flex-container">
      <div class="logoDiv"><img src="../assets/tlogo.png" alt="Cardinal" style="height:3rem; width: 10rem" /></div>
      <div class="searchBox"><search /></div>
      <div class="menuDiv" >
        <font-awesome-icon :icon="['fas', (!showMenu ?'bars': 'xmark')]" class="menuicon" size="2x" @click="openMenu"/>
        <!--<ejs-button isPrimary="true" cssClass="buttons">
          <font-awesome-icon :icon="['far', 'user']" />
          Login
        </ejs-button>-->
      </div>
    </div>
  </ejs-appbar>
  <div class="page-container">
    <transition name="fade">
      <div v-if="showMenu" class="menuContainer">
        <menu-page />
      </div>
    </transition>
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
    // 'ejs-button': ButtonComponent
    'menu-page': menuPage
  },
  data() {
  return {
    showMenu: false,
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
  }
}
}
</script>


<style scoped>

.e-appbar {
    padding: 0px;
}

.page-header{
    height: 6vh;
    width: 100%;
    position: relative;
    border: 0px !important;
}

.page-container {
    position: relative;
    width: 100%;
    height: 94vh;
}

.menuContainer {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 10;
  background-color: hsl(208, 100%, 97%,0.7);
}


.flex-container {
  flex-direction: row;
  align-items: stretch !important;
  justify-content: space-between;
}

.logoDiv {
  max-width: 250px;
  max-height: 100px;
  padding-left: 10rem;
  flex-shrink:0;
  order: 2;
}

.searchBox {
  order: 3;
  padding-right: 1rem;
}

.menuDiv {
  padding-top:10px;
  order: 1;
  min-width: 45px;
}

.menuicon{
  margin-left: 1rem;
  cursor: pointer;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 1s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

@media (max-width: 635px) {
  .flex-container {
    flex-wrap: wrap;
  }
  .page-header{
      height: 13vh;
  }

  .page-container {
      height: 87vh;
  }
  .logoDiv {
    max-width: 200px;
    max-height: 60px;
    padding-left: 1rem;
  }
  .searchBox {
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
