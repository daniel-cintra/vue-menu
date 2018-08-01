# An example of slide menu using Vue and Vue Router

This is a simplified version of the responsive menu I implemented in the Admin Panel of a project some time ago. It uses [Vue.js](https://vuejs.org/) and [Vue Router](https://router.vuejs.org/) and shares some ideas of how to start puting the framework, router, styles and other concepts together.

![vue menu demo](https://github.com/daniel-cintra/vue-menu/blob/master/demo-screencast/menu-vue.gif)

## Customizing

The menu can be easily customized changing:

1. `src/components/Menu.vue` where the root level itens can be found.

2. `src/components/support/menu-data.js` where the childs of root level itens can be found.

3. `src/router.js` where each route can be mapped to load the correspondent component. For the sake of simplicity, with exception of the route `home`, the sections are loaded dynamically in this example.

## Styles

The styles use [Sass](http://sass-lang.com/) css extension language and [BEM Methodology](http://getbem.com/). Each component has the correspondent `.scss` file in `src/styles`, and is imported in `src/App.vue`. This way, is easy to see how the final css is composed and the order of the includes (media queries in the end of the .scss imports).

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
