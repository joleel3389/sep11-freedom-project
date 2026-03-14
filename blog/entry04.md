# Entry 4
##### 3/9/26

### My MVP progress

---

To begin the MVP of my project, I started off with the HTML. I wanted my website to have a basic foundation in HTML before I applied Vue.js to it. For instance, the navigation bar on my website and also the initial placement of where the questionnaire would go. Even though I started with the HTML of my website, I still want to continue learning about my tool, Vue.js, so that I meet all core functions from my tool to apply to my website.

Here's a progress check of my MVP so far:

```html
<nav class="navbar fixed-top bg-body-tertiary navbar-expand-lg" data-bs-theme="dark">
    <div class="container-fluid">
        <span class="navbar-brand mb-0 h1">Calculus study mini-game</span>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
            <li class="nav-item">
                <a class="nav-link" aria-current="page" href="https://www.desmos.com/calculator" target="_blank">Calculator</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#help">Need help?</a>
            </li>
            </ul>
        </div>
    </div>
</nav>

<div class="container-fluid">
    <div class="container" id="#questionaire">
    <h2 class="text-dark">Placeholder question?</h2>
    <input type="radio" name="mcq" value="1" id="Option1"> placeholder <br>
    <input type="radio" name="mcq" value="2" id="Option2"> placeholder <br>
    <input type="radio" name="mcq" value="3" id="Option3"> placeholder <br>
    <input type="radio" name="mcq" value="4" id="Option4"> placeholder <br>
    <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->

    <br>
    <button>Submit</button>
    <br>
    <p></p>
    </div>
</div>
```

<img width="1355" height="592" alt="Screenshot 2026-03-12 3 15 05 PM" src="https://github.com/user-attachments/assets/63af5afa-4b5f-4eeb-bfab-60e92799d971" />

I started with utilizing past knowledge (bootstrap) to make my website feel visually appealing to the eye. I also messed with some CSS and put a placeholder question format that I want to try to build onto later with Vue.js

Meanwhile, for my tool, I worked on learning `v-bind`. What I learned about `v-bind` was that it's used to bind attributes and make them reactive.

`v-bind` also has shorthands, so instead of using `v-bind:attribute="value"`, it can be shortened to `:attribute="value"`. To simplify even more, if the attribute is the same as the value, the equal sign and value can be removed. For example, instead of `:href="href"`, we can use `:href` and it'll be the same.

Within actual code, I've been able to simplify the `v-bind` process like so...

```js
<script setup>
  /*
CHALLENGE: Create a Ref to house "https://vuejs.org/"
           and bind the Ref to our anchor tag's href attribute.
           Use shorthands if you want/can!
*/
import {ref} from 'vue'
const href = ref("https://vuejs.org/")
</script>
```
```html
<template>
  <footer>
      <p>Learn more about me at <a target="_blank" :href>vuejs.org</a></p>
  </footer>
</template>
```

Another small thing to note about `v-bind` is that it works with boolean attributes, for instance.

When learning, I also got used to using reactive arrays over singular reactive elements. For instance, in order to bind the data in the array to our HTML...

```js
<script setup>
/*
CHALLENGE: Create a reactive array of objects to house the Vue facts
TIP: Each object might have a an "adjective" property and "description" property
*/

import {ref} from 'vue'
const facts = ref([
  {
    "adjective": "Lightweight",
    "description": "I am incredibly small and fast! My core library is only around 30KB, so I won't slow you down."
  },
  {
    "adjective": "Approachable",
    "description": "Easy to learn and use, even for beginners. I have a gentle learning curve, clear documentation, and a supportive community."
  },
  {
    "adjective": "Versatile",
    "description": "I can handle everything from simple interactive elements to complex single-page applications. I'm great for small projects and large-scale applications alike."
  },
])
/*
CHALLENGE: Bind the data from the `facts` Ref to elements in the template
*/
</script>
```

As per usual, we would use the double squiggly brackets `{{}}`, but also define the index of the array element we want, like we would usually do in JS itself.

```html
<template>
  <main>
      <section>
          <h2>
              I'm <span class="highlight">{{facts[0].adjective}}</span>
          </h2>
          <p>{{facts[0].description}}</p>
      </section>
      <section>
          <h2>
              I'm <span class="highlight">{{facts[1].adjective}}</span>
          </h2>
          <p>{{facts[1].description}}</p>
      </section>
      <section>
          <h2>
              I'm <span class="highlight">{{facts[2].adjective}}</span>
          </h2>
          <p>{{facts[2].description}}</p>
      </section>
  </main>
</template>
```

In this case, the name of the reactive array is facts, and it holds adjectives and descriptions we can use when we bind the data to the HTML. We just need to specify which element within the array.

### Engineering Design Process

---

In my previous blog, I was on step 2 of the Engineering Design Process (EDP). Throughout this blog, I will be on steps 3 and 4 of the EDP, which are to brainstorm possible solutions (step 3) and plan the most promising solution (step 4). The reason why I'm still on step 3 is because I still want to learn about my FP tool so I can plan throughout working on my MVP how to properly apply my tool where it's needed. I'm also on step 4 because while I'm still learning my FP tool, I'm going to work on my MVP and still make progress, even if it's a little bit. Learning my FP tool is still a part of the brainstorming, and making small progress on my MVP is what I would consider planning the most promising solution (before finalization). By my next blog, hopefully I can focus more on step 4 of EDP, which would be to focus on solely the MVP of my project for me.

### Skills

---

Below are the skills I've learned while working on my blog.
* Debugging
    * When I was continuing to learn about my tool, I paused the instruction before the solution was finished, so I was confused as to why the "solution" seemed to be missing some code. This happened to me when I was dealing with the reactive array example as referenced before. I talked to myself and tried to figure out what was missing and why, until I realized that the solution wasn't actually finished, and there was a second part I should've waited to take notes on. Even though it wasn't a conceptual issue, I learned that problems can have more than one part, and I should wait through the whole thing.
* How to Google
    * With us starting the MVPs of our freedom projects, I was still not finished with my tool, and I had very little idea on how I'd start incorporating it. And so, I asked Google what the most important concepts of Vue.js I'd more likely need to complete the MVP of my project were, and one of them was `v-bind`. This made me decide to finish the `v-bind` lesson on the interactive Vue.js guide I was using, then settle on learning the rest of the important concepts brought up after, such as `@click` and others.

### Next steps

---

For my next steps, I hope to finish learning about the most important Vue.js concepts I need and be more focused on step 4 of EDP (so I can focus more on the MVP of my project).

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
