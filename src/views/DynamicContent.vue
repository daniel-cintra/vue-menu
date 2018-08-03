<template>

  <div class="main-content">

    <div class="main-content__top">

        <h1 class="main-content__title">
          {{sectionName}}
        </h1>

    </div>

    <div class="main-content__body">
        This <strong>{{sectionName}}</strong> page, is dynamic for the sake of simplicity.
    </div>

  </div>

</template>

<script>

import startCase from 'lodash/startCase';

export default {

  name: 'dynamicContent',

  computed: {

    sectionName() {
        return startCase(this.$route.params.sectionSlug);
    }

  }

}

</script>
