<template>
  <div style="padding: 100px">
    <VueSlickCarousel
      v-bind="config.settings"
      ref="c1"
      :asNavFor="config.asNavFor ? $refs.c2 : null"
    >
      <div
        v-for="(index) in [1, 2, 3, 4, 5, 6]"
        :key="index"
      >
        <h1>
          {{ index }}
        </h1>
      </div>
    </VueSlickCarousel>
    <VueSlickCarousel
      v-bind="config.asNavFor.settings"
      ref="c2"
      :asNavFor="$refs.c1"
    >
      <div
        v-for="(index) in [1, 2, 3, 4, 5, 6]"
        :key="`${index}`"
      >
        <h1>
          {{
           index
          }}
        </h1>
      </div>
    </VueSlickCarousel>
  </div>
</template>

<script>
  import VueSlickCarousel from 'vue-slick-carousel'
  // optional style for arrows & dots
  import 'vue-slick-carousel/dist/vue-slick-carousel.css'
  import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

  export default {
    name: 'MyComponent',
    components: { VueSlickCarousel },
    data () {
      return {
        config: {
          settings: { focusOnSelect: true },
          asNavFor: {
            settings: { slidesToShow: 4, focusOnSelect: true },
          },
        }
      }
    },
    mounted() {
      // Comment out these lines and carousels don't sync
      // inspect carousels with chrome vue devtools - each carousel has asHavFor undefined despite props passes
      this.$refs.c1.asNavFor = this.$refs.c2;
      this.$refs.c2.asNavFor = this.$refs.c1;
    },
  }
</script>

<style>
  .slick-next, .slick-prev,
  .slick-next:hover, .slick-prev:hover{
    background: red;
  }
</style>