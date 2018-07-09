# VueJs-Doc

## Vue Syntax
- ``` v-model ``` --> bind a input to a data property. 
- ``` v-on:click ``` --> onHandler click event
- ``` v-for="item in items" ``` --> for loop
- ``` v-for="(item, index) in items" ``` this will give us access to each item index
- ``` v-bind:href ``` is short for ``` :href ``` ``` v-bind ``` shorthand
- ``` v-on:click ``` is short for ``` @click ``` ``` v-on ``` shorthand
- ``` v-bind:class ``` --> to dynamically toggle classes
- ``` v-if, v-else, v-else-if ``` --> if else statements condition 
- ``` v-show ``` --> another option for conditionally displaying an element
- ``` v-bind:is ``` --> Component changes when property changes




## ``` this ``` keyword
when you're refering to the ``` this ``` keyword to the Vue object, it will represent the Vue instance.

## ``` v-for ``` how to use for loop, you can also use ``` of ``` instead of ``` in ``` so that it is closer to Javascript syntax for iterations
``` 
// html
<ul id="example-2">
  <li v-for="(item, index) in items">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
  </li>
</ul>

// js 
var example2 = new Vue({
  el: '#example-2',
  data: {
    parentMessage: 'Parent',
    items: [
      { message: 'Foo' },
      { message: 'Bar' }
    ]
  }
})

// you can provide arguments to 'v-for'
<div v-for="(value, key, index) in object">
  {{ index }}. {{ key }}: {{ value }}
</div>

```

## Creating custom elements. reusable self-contain components, each time you use a component, a new instance of it is created.
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
> another one.
``` 
// Define a new component called button-counter
Vue.component('button-counter', {
  data: function () {
    return {
      count: 0
    }
  },
  template: '<button v-on:click="count++">You clicked me {{ count }} times.</button>'
})

<div id="components-demo">
  <button-counter></button-counter>
</div>

new Vue({ el: '#components-demo' })
```

## Binding inline styles
``` 
// html
<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>

// js 
data: {
  activeColor: 'red',
  fontSize: 30
}
```

## Content Distribution with Slots
- passing content to a component
```
<alert-box>
  Something bad happened.
</alert-box>

Vue.component('alert-box', {
  template: `
    <div class="demo-alert-box">
      <strong>Error!</strong>
      <slot></slot>
    </div>
  `
})
```


###### It is often a good idea to bind to a style object directly so that the template is cleaner
```
// html 
<div v-bind:style="styleObject"></div>

// js 
data: {
  styleObject: {
    color: 'red',
    fontSize: '13px'
  }
}

```

## Vue methods
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

## Vue using ``` key ```
- adding a unique key to each element to distingish the difference between the multiple components.
```
<template v-if="loginType === 'username'">
  <label>Username</label>
  <input placeholder="Enter your username" key="username-input"> // here
</template>
<template v-else>
  <label>Email</label>
  <input placeholder="Enter your email address" key="email-input"> // and here
</template>

```

## Object Change Detection
- Vue cannot detect property addition or deletion
- However, it's possible to add reactive proerties to a nested object using the ``` Vue.set(object, key, value) ``` method
```
var vm = new Vue({
  data: {
    userProfile: {
      name: 'Anika'
    }
  }
})

Vue.set(vm.userProfile, 'age', 27)
              or 
vm.$set(vm.userProfile, 'age', 27) // this is an alias for the global Vue.set
```



## Computed Caching vs Methods
- the following computed property will never update, because Date.now() is not a reactive dependency
``` 
computed: {
  now: function () {
    return Date.now()
  }
}
```
## General (useful) informations about VueJs
- Generally speaking, ``` v-if ``` has higher toggle costs while ``` v-show ``` has higher initial render costs. So prefer v-show if you need to toggle something very often, and prefer ``` v-if ``` if the condition is unlikely to change at runtime.
- It is recommended to provide a ``` key ``` with ``` v-for ``` whenever possible, unless the iterated DOM content is simple, or you are intentionally relying on the default behavior for performance gains.
``` 
<div v-for="item in items" :key="item.id">
  <!-- content -->
</div>
```
- ``` filter(), concat() and slice() ```, which do not mutate the original array but always return a new array


## Vue Directives
Directives are special attributes with the ``` v- ``` prefix.


<--------------------------------------------------------------------------------------

Vuex for keeping track of states

VueStrap - Bootstrap components built with Vue.js - No jQuery, bootstrap.js, or any 3rd party plugins requred.
