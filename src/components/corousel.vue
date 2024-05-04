<template>
  <div class="control-container">
    <ejs-carousel indicatorsType="Dynamic">
      <e-carousel-items>
        <e-carousel-item template="Cardinal"></e-carousel-item>
        <template v-slot:Cardinal>
          <figure class="img-container">
            <img src="../assets/products/j1.jpg" alt="Cardinal"
              style="height: 100%; width: 100%" />
            <figcaption class="img-caption">Journals</figcaption>
          </figure>
        </template>
        <e-carousel-item template="kingfisher"></e-carousel-item>
        <template v-slot:kingfisher>
          <figure class="img-container">
            <img src="../assets/products/j2.jpg" alt="kingfisher"
              style="height: 100%; width: 100%" />
            <figcaption class="img-caption">Productivity Tracker</figcaption>
          </figure>
        </template>
        <e-carousel-item template="keel-billed-toucan"></e-carousel-item>
        <template v-slot:keel-billed-toucan>
          <figure class="img-container">
            <img src="../assets/products/wkp.jpg" alt="keel-billed-toucan"
              style="height: 100%; width: 100%" />
            <figcaption class="img-caption">Weekly Planner</figcaption>
          </figure>
        </template>
        <e-carousel-item template="yellow-warbler"></e-carousel-item>
        <template v-slot:yellow-warbler>
          <figure class="img-container">
            <img src="../assets/products/trp.jpg" alt="yellow-warbler"
              style="height: 100%; width: 100%" />
            <figcaption class="img-caption">Travell Planner</figcaption>
          </figure>
        </template>
        <e-carousel-item template="bee-eater"></e-carousel-item>
        <template v-slot:bee-eater>
          <figure class="img-container">
            <img src="../assets/products/dp.jpg" alt="bee-eater"
              style="height: 100%; width: 100%" />
            <figcaption class="img-caption">Daily Planner</figcaption>
          </figure>
        </template>
      </e-carousel-items>
    </ejs-carousel>
  </div>
</template>

<script>
import { 
    CarouselComponent,
    CarouselItemDirective,
    CarouselItemsDirective, } from '@syncfusion/ej2-vue-navigations';

export default {
    name: 'corousel',
    components: {
    "ejs-carousel": CarouselComponent,
    "e-carousel-items": CarouselItemsDirective,
    "e-carousel-item": CarouselItemDirective,
  }
};
</script>

<style scoped>

.control-container {
  height: 100%;
  margin: 0 auto;
  width: 100%;
}

.img-container {
  height: 100%;
  margin: 0;
}

.img-caption {
  color: #fff;
  font-size: 5rem;
  position: absolute;
  bottom: 3rem;
  width: 100%;
  text-align: right;
}
</style>