## Vue.js <button> opening a new tab

One thing I found difficult in remembering how to do was making a button in VueJS act as an `<a>` tag and open a link via a new tab. Fortunately, this was way easier than I thought! 

```html
<​button @​click​=​"​gotoLink()​">
  Click me! 
</button>
```

```js
methods: {
​  gotoLink​() {
​    window​.​open​(​'https://workingunittests.com'​, ​'​_blank​'​);
  }
} 
```