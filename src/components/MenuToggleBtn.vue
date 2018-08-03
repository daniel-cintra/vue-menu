<template>

  <a
  href="#"
  @click.prevent="toggleMenu"
  class="btn menu-toggle-btn"
  >
    <i class="fa fa-bars" aria-hidden="true"></i>
  </a>

</template>

<script>

export default {

   methods: {

    toggleMenu() {
      window.bus.$emit('menu/toggle');
    },

  },

};

</script>
