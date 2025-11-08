# Entry 1: Deciding on my freedom project tool
##### 11/3/25

### What was my tool and why did I choose it?

---

For my project, I decided to choose the tool Vue JS. Vue JS is a friendly and simple JavaScript framework to help build interfaces. The reason why I chose Vue JS was because I was between React JS or Vue JS to help me make my calculus memorization game, but the way you had to download React JS locally was difficult, due to school device restrictions. However, I found out that Vue JS was simpler, and I was able to locally be able to use Vue JS with no problems, so I wouldn't have had to been stuck using a CDN. I also found Vue JS to be more friendly and easier to comprehend than Vue JS.

To experiement with Vue JS, I used the [official Vue documentation](https://vuejs.org/guide/quick-start.html) and I used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr). My tinkering was done [here](../tool/vue-js-testing).

I tinkered with Vue JS by first testing it while using a CDN. I discovered that Vue JS can still run smoothly with a CDN, but then I tested Vue JS locally, and preferred to view Vue JS code locally. I discovered that when you make a Vue project locally, when you view the preview it automatically updates on the page, so you don't need to reload like you'd do with `http-server` while using a CDN. Additionally, when you make a Vue JS project locally, you're able to code JS, HTML, and CSS on the same file, which is more convinent than using a CDN. Using a CDN also means you need to use more code, such as `.mount` to apply your changes to the specific element.

Below shows the difference between the JS code you would need between a CDN and using Vue JS locally.

* Using a CDN
    ```JS
    const { createApp, ref } = Vue
    createApp({
        setup() {
            const name = ref("Jolee")
            return {name}
        }
    }).mount("#myApp")
    ```

* Using Vue JS locally
    ```JS
    <script setup>
    /*
    CHALLENGE: Make the copyright year dynamic and blue
    IN SCRIPT: Create a new ref to house a different year
    IN TEMPLATE: Change the static "2025" to render the new ref
    IN STYLE: Target the paragraph tag in the footer and make it blue
    */
    import {ref} from 'vue'
    const name = ref('Rachel')
    const emoji = ref('✌🏻')
    const year = ref('2026')
    </script>
    ```

The following inputs don't give the same outcomes, but it goes to show that when you don't use a CDN and use Vue JS locally, it's easier as all you need to do is import the Vue function, and you can just define your Vue function values, which is `{ref}` in my case (for both examples). Using a CDN includes `.mount`, a setup function, a return statement, and just more than using Vue locally.

Output comparison (top to bottom)
<img width="377" height="250" alt="2025-10-12 17_47_11-Vue JS testing and 5 more pages - Personal - Microsoft​ Edge" src="https://github.com/user-attachments/assets/fea091ab-3025-42e5-90f1-27ea5e734e25" />

<img width="1665" height="897" alt="2025-11-08 11_01_15-Window" src="https://github.com/user-attachments/assets/780c4a6c-02a2-481b-8204-61d5fae0c353" />

### Engineering Design Process

---

I'm currently in the first step of the engineering design process, which is to define the problem. My problem is "how can I use a tool of my choice to create a calculus memorization game?" I hope to address this problem by properly utilizing my tool throughout the year to make a user interface that allows users to work on recalling their calculus concepts effectively. For my next steps, I plan to research more into the problem, so I'll continue to learn more about the tool I want to use in order to solve my problem and also find calculus concepts I could potentially put in my project.

### Skills

Below are the skills I've learned while working on my blog.
* **Embracing failure**
    * As mentioned earlier, I first tried to test out with React JS to solve my problem. However, React JS was harder to set up locally and kind of a headache, but I tried to persevere and decided to go to my backup tool, which was Vue JS. Vue JS worked way smoother for me, and I was able to locally use it in my IDE. I didn't give up with the task despite failure and found an alternative.
* **Consideration**
    * When I started my project, I already had a general idea that I wanted my project to be a math memorization game. However, this was the time where I was also considering what tool to use to solve my problem. I had to be considerate of how users would interact with my website, and make sure I chose the tool that would correctly represent my project well. So I after asking for advice from [ChatGPT](https://chatgpt.com/), I decided Vue JS would be the best fit. 

### Next Steps

For my next steps, I plan to research more about my tool in depth to effectively use it, and to also review the calculus concepts myself to figure out which I should incorporate into my project.

[Next](entry02.md)

[Home](../README.md)
