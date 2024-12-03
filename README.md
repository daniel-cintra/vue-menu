# Repository Archived

This repository has been archived and is no longer maintained.

## An example of slide menu using Vue and Vue Router

This is a simplified version of the responsive menu I implemented in the Admin Panel of a project some time ago. It uses [Vue.js](https://vuejs.org/) and [Vue Router](https://router.vuejs.org/) and shares some ideas of how to start puting the framework, router, styles and other concepts together.

![vue menu demo](https://github.com/daniel-cintra/vue-menu/blob/master/demo-screencast/menu-vue.gif)

## Customizing

The menu can be easily customized for your needs changing:

1. `src/components/Menu.vue` where the root level itens can be found.

2. `src/components/support/menu-data.js` where the childs of root level itens can be found.

3. `src/router.js` where each route can be mapped to load the correspondent component. For the sake of simplicity, with exception of the `home` route, the sections are loaded dynamically in this example.

### Customizing: src/components/Menu.vue

You can find the root level itens of the menu here. In this example, the four root itens (Home, Products, Customers, Account) are coded directly in the Menu component, but could be set as data properties or loaded from external resources.

Example of one root level iten definition:

```vue
    <template>

    ...
    <li>
        <a
        href="#"
        @click.prevent="updateMenu('products')"
        :class="highlightSection('products')"
        >
          <i class="fa fa-tag menu__icon" aria-hidden="true"></i>
          Products
          <i class="fa fa-chevron-right menu__arrow-icon" aria-hidden="true"></i>
        </a>
    </li>
    ...

    </template>
```

### Customizing: src/components/support/menu-data.js

You can set the childs of the root itens here.

```javascript
export default {

  // home is a section without childs, set as an empty array
  home: [],

  products: [

    {
      type: 'title',
      txt: 'Products',
      icon: 'fa fa-tag context-menu__title-icon',
    },

    {
      type: 'link',
      txt: 'List Products',
      link: '/page',
    },

    {
      type: 'link',
      txt: 'Add New Product',
      link: '/page',
    },

    {
      type: 'link',
      txt: 'Manage Categories',
      link: '/page',
    },

  ],
  ...

}
```

### Customizing: src/router.js

Add routes and components mappings here.

```javascript
import Vue from 'vue'
import Router from 'vue-router'
import Home from './views/Home.vue'

Vue.use(Router)

export default new Router({
  mode: 'history',

  routes: [

    // loads Home component
    {
      path: '/',
      name: 'home',
      component: Home
    },
    {
      path: '/page/:sectionSlug',
      name: 'dynamicContent',
      // route level code-splitting
      // this generates a separate chunk (dynamicContent.[hash].js) for this route
      // which is lazy-loaded when the route is visited.
      component: () => import(/* webpackChunkName: "dynamicContent" */ './views/DynamicContent.vue')
    },

  ]
})
```

## Styles

The styles use [Sass](http://sass-lang.com/) css extension language and [BEM Methodology](http://getbem.com/). Each component has the correspondent `.scss` file in `src/styles`, and is imported in `src/App.vue`. This way, is easy to see how the final css is composed, and the order of the included files (note the media queries in the end of the .scss imports).

```sass
@import 'styles/layout.scss';
@import 'styles/menu-toggle-btn.scss';
@import 'styles/menu.scss';
@import 'styles/content-overlay.scss';
@import 'styles/media-queries.scss';
```

## Demo
There's an [online demo here](https://vue-menu.danielcintra.site/).

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Lints and fixes files
```
yarn run lint
```

## License
This menu is licensed under the [Mit License](https://opensource.org/licenses/MIT).
