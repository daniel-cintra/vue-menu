<template>

  <div class="main-content">

    <div class="main-content__top">
        <h1 class="main-content__title">
            Home
        </h1>
    </div>

    <div class="main-content__body">

      <p>
        Hi! This is a simplified version of the responsive menu I implemented in the
        Admin Panel of a project some time ago. Maybe it can help newcomers to
        <a href="https://vuejs.org/">Vue.js</a> and <a href="https://router.vuejs.org/">Vue Router</a>
        to have some ideas of how to start puting the framework, router, styles
        and other concepts together.
      </p>

      <p>
        You can find the Github Repository of this menu
        <a href="https://github.com/daniel-cintra/vue-menu">here</a>.
      </p>

      <p>
        The menu can be easily customized changing:
      </p>

      <ol>

        <li>
          <strong>src/components/Menu.vue</strong>
          where the root level itens can be found.
        </li>

        <li>
          <strong>src/components/support/menu-data.js</strong>
          where the childs of root level itens can be found.
        </li>

        <li>
          <strong>src/router.js</strong>
          where each route can be mapped to load the correspondent component.
          For the sake of simplicity, with exception of the <strong>home route</strong>, the
          sections are loaded dynamically in this example.
        </li>

      </ol>

    </div>

  </div>

</template>

<script>

export default {
  name: 'home'
}

</script>
