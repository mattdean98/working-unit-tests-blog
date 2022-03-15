## Vue.js Wait for a Child Component to Mount

# Introduction
Ideally - we want our components to be kinda "dumb". Mostly just displaying data or gathering input from the user - the front end components shouldn't be smart enough to know what to do with said info once they have it. 

Usually this means we need to tell another portion of the app to handle more complex stuff. Be it Vuex to handle connecting to our API or to manage our data state that is read by other "dumb" components.

Today I learned a new thing, and that is how to listen to a child component's `mounted` lifecycle method before doing something. 

# The Code
```js
<CustomComponentName @hook:mounted="onChildComponentMount()"/>
```

```js
methods: {
  onChildComponentMount() {
    console.log('CustomComponentName mounted!');
  }
}
```

# Conclusion
My take away today is this:
> If it feels harder than it should be - you're probably doing it wrong.

Is this new to you too? Let me know in the comments!