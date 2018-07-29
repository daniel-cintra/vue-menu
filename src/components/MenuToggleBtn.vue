<template>

    <a
    href="#"
    class="btn menu-toggle-btn"
    @click.prevent="toggleMenu"
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
