# Entry 3
##### 2/2/26

### My tool learning process after winter break

---

Throughout the winter break, my goal was to learn the building block of reactivity and move on from components. My progress following after the winter break includes learning about reactive state, reactive state variables, and refs. To elaborate, a reactive state signifies when an element is reactive, and so Vue will constantly be updating the element automatically. Reactive state variables use `ref()` in order to make a constant variable and render. These refs should always be imported, like the example below:

```js
<script setup>
    import {ref} from 'vue'
    const quote = ref("First, solve the problem. Then, write the code.")
    /*
    CHALLENGE: Create a reactive variable to house the author
    */
</script>
```

When we import refs like this; `{ref}`, this allows us to override the hard coded element. The hard coded element we have as a constant variable would be assigned the new value we put in the parameters of `ref()`, and will be updated live. Meaning anytime we change the value within `ref()`, the change will be seen live without needing to reload the page!

This live property of refs can be seen below as I play with the title:

Besides assigning a new value to a reactive element (using ref), there's another way to override the value for your element. This method overwrites whatever you have written in the parameters of `ref()`. For instance, if I had the following reactive element:

```js
 <script setup>
    import {ref} from 'vue'
    const title = ref("Quote Generator")
</script>
```

Shown as `{{title}}` in the HTML section (as reactive elements need double swiggly brackets around their variable name):

```html
<template>
    <header>
        <h1>{{title}}</h1>
    </header>
</template>
```

**NOTE**: The parameters of `ref()` are not only limited to strings. You can use booleans, arrays, or numbers, but make sure quotations are else where when you need them.

I'm able to override the value assigned to "title" (using `ref()`) by using `title.value = "Programming Quotes"` instead. For example:

```js
 <script setup>
    import {ref} from 'vue'
    const title = ref("Quote Generator")

    title.value = "Programming Quotes"
</script>
```
Within the HTML, you can still keep `{{title}}`, so that Vue knows to update it. Disregarding the value assigned to title using `ref()`, the resulting page will appear like this.



### Engineering Design Process

---

In my previous blog, I was on step 2 of the engineering design process. Step 1 is long finished, but I think I'm still on step 2 of the engineering design process, which is to research the problem. I still need to continue to research my freedom project tool in order to effectively use it, as once I finish learning reactivity completely I may have the chance to learn Vue images. Therefore, I'm still going to be looking into the rest of Vue before brainstorming on what to do with my Vue knowledge to solve my problem. I hope by my next blog, I'll be able to finish Vue images (my last concept) and move onto step 3 of the engineering design process (to brainstorm possible solutions for my problem).

### Skills

---

Below are the skills I've learned while working on my blog.
* Organization
    * To learn my tool, I've been using [Scrimba](https://scrimba.com/). The thing with [Scrimba](https://scrimba.com/) is that they have exercises I can practice with on their own site, which made me forget to update my own Vue file within my actual freedom project. So while working on this blog, I remembered to also have the code I do on Scrimba organized into my own Vue file under my freedom project, so that it's easier to refer back to. This is important, as I was trying to refer back on how to use refs (that I worked on during the winter break), but since I never updated the Vue file under my freedom project, I had to go back to the actual [Scrimba](https://scrimba.com/) lesson(s) to find the full code I was looking for. Hence, organization is a vital skill to have in order to make it easier to look back on your previous works.
* Time management
    * When I was learning reactivity for Vue, it was during the winter break. This is a significant factor to consider, as during the winter break I would assume that most students would end up doing their work last minute. Even though I didn't end up doing my learning log the moment the break started, I feel satisfied with the fact that I wasn't cramming my learning log the day before we went back to school. Thus, while working during the winter break, I've successfully improved my time management by not working on stuff last minute, and working a bit early.

### Next Steps

For my next steps, I plan to continue working on reactivity, but I would additionally hope that I'd have enough time to take notes for or learn Vue images-the last building block of Vue-in order to have majority of what I need to know for my MVP Freedom Project. My long term goal is to hopefully learn all of Vue's main building blocks, so that I can utilize all the information I know about those Vue building blocks on my future MVP Freedom Project.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
