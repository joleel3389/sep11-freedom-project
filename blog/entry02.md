# Entry 2: Learning my tool - Vue.js
##### 12/15/25

### How have I been learning my tool?

---

For my project, I've started to learn Vue.js as my definite tool. Throughout the past few weeks, I've been solidifying my understanding of structural components and how to use them in a way your code will look more organized. This is done in a way where the 3 structural components (header, main, and footer) would be in separate files that are connected to the main `App.vue` page. These structural components would be connected to the main `App.vue` page through importing, where capitalization matters. For example, to start off, you'd make the 3 structural component files into the `src/components/` file path like so:

<img width="279" height="216" alt="2025-12-14 17_11_31-Window" src="https://github.com/user-attachments/assets/5ff6a40c-6c34-4516-9ddc-a17ff4252b2e" />

In which the purpose of these new files are to simplify the amount of code used on our original `App.vue` file. So instead of having so many indentations on `App.vue` for each structural component, they're able to have their own code live in their own respective files (that will still appear the same in a preview!).

Then, to make sure these new structural component files are connected to the main `App.vue` file, we'd use the following code in our `<script>` tags in `App.vue` like shown below:

```js
<script setup>
    /*
    CHALLENGE: Turn the provided HTML/CSS mockup into a Vue app that
            uses three components: Header, Main, and Footer.
            Make sure you use all the provided CSS!
    */
    import Header from '@/components/Header.vue'
    import Main from '@/components/Main.vue'
    import Footer from '@/components/Footer.vue'
</script>
```

The `@` alias here is equivalent to the absolute file path of `src/`, no matter what. So the `@` alias is more useful to use when importing our structural components compared to relative traversing (using `.`). Once we have our three structural components imported, we should also reference them in the HTML `<template>` tags in `App.vue`, like shown below:

```html
<template>
    <Header/>
    <Main/>
    <Footer/>
</template>
```

This brings everything from the separate structural component files back into our `App.vue`. By importing in our `<script>` tags and referencing the structural components in our HTML, the code we would put inside the new structural component files would be connected back to the main `App.vue` page to be shown in the preview.

Finally, for our Vue app to function as it would without simplifying the layout/structural components usage, we would need to move the original code into their respective parts, which would be shown below!

<img width="600" height="428" alt="2025-12-14 19_18_50-Window" src="https://github.com/user-attachments/assets/d7bc5d05-82af-4195-bb6e-581c4e5c1286" />
<img width="652" height="510" alt="2025-12-14 19_19_07-Window" src="https://github.com/user-attachments/assets/98e44dbc-12e6-4f2a-95fd-d62b0f5d6200" />
<img width="890" height="767" alt="2025-12-14 19_19_47-Window" src="https://github.com/user-attachments/assets/d40f47e2-4f35-4f96-8eeb-ac933fc55558" />
<img width="917" height="610" alt="2025-12-14 19_19_58-Window" src="https://github.com/user-attachments/assets/1ffac98d-7a47-483c-a394-1cad63122ba3" />
<img width="919" height="418" alt="2025-12-14 19_20_07-Window" src="https://github.com/user-attachments/assets/93bb6416-c030-42c5-97c9-3c97d914c0b0" />

Additionally, another last step for our preview to look as we want it would be to consider the addition of our own `main.css` file, that's held in the `src/assets/` folder. This is in case we want CSS that'll apply to the whole app, not just one component!

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');

* {
    margin: 0;
    padding: 0;
    font-family: 'Inter', sans-serif;
    box-sizing: border-box;
}

body {
    background-color: #40b883;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

#app {
    background-color: #eee;
    width: 80%;
    max-width: 700px;
    margin: 0 auto;
    padding: 35px;
    border-radius: 15px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
}


span.highlight {
    color: #40b883;
}
```

With the last addition of our `main.css`, everything comes together and appears in the preview, but simplified and clean in our `App.vue`. We won't have a ton of code to scroll through on one page, but instead code separated and organized into their own pages, which would make it easier to look for bugs. The following image below shows the final outcome/preview:

<img width="505" height="615" alt="2025-12-21 15_36_11-Window" src="https://github.com/user-attachments/assets/c9630a02-9d0b-423f-b7b2-13bd5e907bc6" />

### Engineering Design Process

---

I've passed stage 1 of the engineering design process, and I'm about to enter the 2nd stage of the engineering design process. Stage 2 of EDP (engineering design process) is to continue to research the problem. In my case, I'm going to continue to cover/learn about other concepts within Vue, like reactivity. The past couple of weeks, I've focused on refining my understanding regarding components, but now is a good time to switch focus, so I can comprehend all of Vue's functions to properly apply them when the time comes.

### Skills

---

Below are the skills I've learned while working on my blog.
* Growth Mindset
    * When I was recording the stuff I was learning on my learning log, I encountered issues with the website I was using ([Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr:about)). The most annoying issue was that when I was completing a challenge, the website would mark my attempt as wrong whenever it required me to add new files to the workspace. This was very frustrating at first, because when using components, my new structural component files were definitely spelt correctly and put in the correct file. However, I was able to be patient with the website and tried to instead check my work later as I allowed the video to continue playing, to which I think the problem was within the website, because my work was always identical to what was done in the video (despite being marked wrong by Scrimba).
* Attention to detail
    * Despite the issues I've mentioned earlier when dealing with [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr:about), I've found that when learning my tool, I like to pay close attention to capitalization. This is important, as Vue has its own naming convention, where any file ending with `.vue` (such as the structural components: header, main, footer) will always have the first letter capitalized. For instance, `footer.vue` should really be `Footer.vue`. Therefore, my attention to detail pays off especially whenever I have to reference back to the structural component files when I import them.

### Next Steps

For my next steps, I plan to set a goal for my tool over the winter break. My goal for the winter break is to move on from learning the building block of components to moving on to learning about Vue reactivity. I would like to move on from reinforcing the concept of components in Vue to putting my focus on another core building block of Vue. Which means I'll continue to research more about my problem/tool.

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
