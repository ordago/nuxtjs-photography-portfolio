<template>
  <div>
    <menu-superior/>
    <Nuxt />
  </div>
</template>

<script>
import MenuSuperior from '~/components/MenuSuperior.vue';
export default {
components: {MenuSuperior},
  data() {
    return {
      show: false
    }
  }
}
</script>