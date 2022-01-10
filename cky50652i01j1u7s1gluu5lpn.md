## Dynamic Images in Vue.js

# The problem
One thing I have encountered a few times is needing to choose dynamically between a static list of images to display. In Vue.js I kept this in my `/assets` folder, organized in a way that made sense, but I had issues actually loading the image.

An example of would work for a set static image is as follows:
```html
<img src="@/assets/images/imagename.png" />
```

One option would be to have a list of `<img>` elements, and use `v-if` to determine which one to show. There are many reasons **not** to do this but it did cross my mind.

# What didn't work
My first attempt was getting an image/asset name from a [prop](https://vuejs.org/v2/guide/components-props.html) and loading that into the `<img>` element. 
```html
<figure class="image">
  <img :src="image" />
</figure>
```
```js
props: {
  image: {
    type: String,
    default: '', // example: '@/assets/images/imagename.svg'
  },
},
```

The problem with this method is the `@/assets/...` is handled by Vue, and when passed as a prop is either treated as a literal **or** not handled right regarding filename hashing. Either way - no image could be found.


# What seemed to work for me
One flicker of light hit me as I was trying out options and found that wrapping a `require()` statement in a `computed` getter seemed to do the trick - as that would allow Vue's hands to get a hold of the `@/assets/...` alias and properly find the image amidst the filename hashing. Needless to say, it was a good day.

```html
<figure class="image">
  <img :src="imagePath" />
</figure>
```

```js
props: {
  image: {
    type: String,
    default: '', // example: 'imagename.svg'
  },
},

computed: {
  imagePath() {
    if (this.image !== '') {
      return require(`@/assets/path/to/image/${image}`);
    }
  }
}
```

Did this help you? Perhaps there are other ways to do this? Is there a better way to do this that I am drawing a blank on? Let me know in the comments below, I would love to hear from you!