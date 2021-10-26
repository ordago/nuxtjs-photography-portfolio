<template>
  <PhotoSlide/>
</template>

<script>
import PhotoSlide from '~/components/home/PhotoSlide.vue';
export default {
components: {PhotoSlide},
  data() {
    return {
      show: false
    }
  }
}
</script>