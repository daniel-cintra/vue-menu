<template>

  <div
  @click.prevent="closeMobileMenu"
  class="content-overlay"
  ></div>

</template>

<script>

export default {

   methods: {

    closeMobileMenu() {
      window.bus.$emit('menu/toggle');
    },

  },

};

</script>
