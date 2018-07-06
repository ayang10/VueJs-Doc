# VueJs-Doc

## Vue Syntax
- ``` v-model ``` --> bind a input to a data property. 
- ``` v-on:click ``` --> onHandler click event
- ``` v-for="item in items" ``` --> for loop
- ``` v-for="(item, index) in items" ``` this will give us access to each item index


### ``` this ``` keyword
when you're refering to the ``` this ``` keyword to the Vue object, it will represent the Vue instance.

Creating custom elements. reusable self-contain components
```
// html
<whatever title="Bread"></whatever>

// js
Vue.component('whatever', {
  props: ['title'],
  template: '<li>{{ title }}</li>'
});

// creating new instance
new Vue({ 
  el: '#app'
}
```
### Vue methods
```
new Vue({ 
  el: '#app',
  data: {
  // these are properties
    total: 0,
    items: [{ title: 'Item 1' },
            { title: 'Item 2' }]
  },
  methods: {
    addItem: function() {
      console.log('do something'); // you can call this method at 'addItem'
    }
  }
}

```


### Vue Directives
Directives are special attributes with the ``` v- ``` prefix.


<--------------------------------------------------------------------------------------

Vuex for keeping track of states

VueStrap - Bootstrap components built with Vue.js - No jQuery, bootstrap.js, or any 3rd party plugins requred.
