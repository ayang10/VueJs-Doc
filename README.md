# VueJs-Doc

## Vue Syntax
v-model --> bind a input to a data property. 
v-on:click --> onHandler click event







Creating custom elements. reusable self-contain components
```
// html
<whatever title="Bread"></whatever>

// js
Vue.component('whatever', {
  props: ['title'],
  template: '<li>{{ title }}</li>'
});

new Vue({ // creating new instance
  el: '#app'
}
```

Vuex for keeping track of states

VueStrap - Bootstrap components built with Vue.js - No jQuery, bootstrap.js, or any 3rd party plugins requred.
