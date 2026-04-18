# Entry 5
##### 4/13/26

### MVP product

---

To finish off the MVP of my project, I learned Vue.js concepts like `v-if`, `:key`, `v-model`, Vue transitions. Not regarding my tool, I looked over concepts like CSS transitions, JS `setTimeout()`, and JS `sort()`. The way I used all of these concepts varied.

I used `v-if` in order to toggle most of the containers on my project and also the transitions that trigger whether you got an answer wrong or right (which I'll discuss later). For example, here's the HTML portion of my code:

```html
<template>
    <div class="container-fluid" id="home" v-if="!play">
        <img src="/hachi-nerd-sprite.png" alt="NERDY hachiware" class="icon">
        <p class="text-light-dark center baloo-2-regular">Choose your deck:</p>
        <button class="btn text-dark center poppins-regular" @click="unitCircle()">Unit circle</button>
    </div>
    <div class="container-fluid" id="score" v-if="play">
        <p class="text-light-dark left baloo-2-regular">Score: {{score}}</p>
        <p class="text-light-dark right baloo-2-regular">{{questionNumber}}/10</p>
    </div>
    <div class="container-fluid" id="unitCircle" v-if="!done && play && setCircle">
        <div class="container" id="questionaire">
            <h2 class="text-dark baloo-2-regular">{{questionaire[questionNumber].question}}</h2>
            <div class="baloo-2-regular" id="bulletPoints">
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[0]" id="Option1" v-model="userChoice"> {{questionaire[questionNumber].choices[0]}} <br>
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[1]" id="Option2" v-model="userChoice"> {{questionaire[questionNumber].choices[1]}} <br>
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[2]" id="Option3" v-model="userChoice"> {{questionaire[questionNumber].choices[2]}} <br>
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[3]" id="Option4" v-model="userChoice"> {{questionaire[questionNumber].choices[3]}} <br>
                <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->
            </div>

            <button class="btn text-dark poppins-regular" @click="checkAnswer()">Submit</button>
            <Transition name="correct">
                <img src="/hachi-cheeky-sprite.png" alt="cheeky hachiware" class="icon" v-if="correct" :key="questionNumber">
            </Transition>
            <Transition name="wrong">
                <img src="/hachi-sad-sprite.png" alt="sad hachiware" class="icon" v-if="wrong" :key="questionNumber">
            </Transition>
        </div>
    </div>
    <div class="container-fluid" id="complete" v-if="done && play">
        <img src="/hachi-cheer-sprite.png" alt="cheerleader hachiware" class="icon">
        <p class="text-light-dark center baloo-2-regular">Deck complete!</p>
        <div>
        <button class="btn text-dark center poppins-regular" @click="home()">Home</button>
        <button class="btn text-dark center poppins-regular" @click="refresh()">Play again?</button>
        </div>
    </div>
</template>
```

As you can see, certain containers will only be toggled if a certain variable is true. Take this specific container, for example:

```html
<div class="container-fluid" id="complete" v-if="done && play">
        <img src="/hachi-cheer-sprite.png" alt="cheerleader hachiware" class="icon">
        <p class="text-light-dark center baloo-2-regular">Deck complete!</p>
        <div>
        <button class="btn text-dark center poppins-regular" @click="home()">Home</button>
        <button class="btn text-dark center poppins-regular" @click="refresh()">Play again?</button>
        </div>
</div>
```

Similar to JS conditionals, if my ref variables (which are declared in my script already) `done` and `play` are true, then this container will be toggled on to indicate that the user completed a deck. Similarly, other containers will also be toggled when their respective conditions are met. 

For `v-model`, I used it on the radio buttons for the actual questions, as shown here:

```html
<div class="container" id="questionaire">
            <h2 class="text-dark baloo-2-regular">{{questionaire[questionNumber].question}}</h2>
            <div class="baloo-2-regular" id="bulletPoints">
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[0]" id="Option1" v-model="userChoice"> {{questionaire[questionNumber].choices[0]}} <br>
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[1]" id="Option2" v-model="userChoice"> {{questionaire[questionNumber].choices[1]}} <br>
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[2]" id="Option3" v-model="userChoice"> {{questionaire[questionNumber].choices[2]}} <br>
                <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[3]" id="Option4" v-model="userChoice"> {{questionaire[questionNumber].choices[3]}} <br>
                <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->
            </div>
```

`v-model` can be used on multiple types of inputs, in that I choose to use it with radio buttons. What `v-model` helps do specifically is that it'll bind the `:value` of the chosen radio button and store it to my ref variable `userChoice`. This is especially useful for my `checkAnswer` function as seen here:

```js
function checkAnswer(){
    // look into the array, then get the index for current question, then find the correct property
    if(userChoice.value === questionaire.value[questionNumber.value].correct){ 
        correct.value = true;
        wrong.value = false;
        score.value++;
        questionNumber.value++;
        userChoice.value = undefined;
        // after set time set the value of correct back to false for the css transition animation
        setTimeout(function(){
            correct.value = false
        }, 900);
        if(questionNumber.value === 10){
            done.value = true;
        }
    } else {
        correct.value = false;
        wrong.value = true;
        // after set time set the value of wrong back to false for the css transition animation
        setTimeout(function(){
            wrong.value = false
        }, 900);
    }
}

import {ref} from 'vue'
const questionaire = ref([
{
    "question": "What's the angle at 3π/4?",
    choices: ["175°","150°","135°","120°"],
    correct: "135°"
},
{
    "question": "What's the angle jump at every π/4th of a jump?",
    choices: ["45°","25°","30°","60°"],
    correct: "45°"
},
{
    "question": "What are the coordinates of 11π/6?",
    choices: ["(√3/2, 1/2)","(√3/2, -1/2)","(√2/2, -√2/2)","(√2/2, √2/2)"],
    correct: "(√3/2, -1/2)"
},
{
    "question": "What's the angle at 7π/6?",
    choices: ["240°","210°","180°","225°"],
    correct: "210°"
},
{
    "question": "What's the angle jump at every π/6th?",
    choices: ["30°","60°","90°","15°"],
    correct: "30°"
},
{
    "question": "What's the angle jump at every π/2th?",
    choices: ["30°","60°","90°","15°"],
    correct: "90°"
},
{
    "question": "What's the angle jump at every π/3th?",
    choices: ["30°","60°","90°","15°"],
    correct: "60°"
},
{
    "question": "What are the coordinates of 5π/4?",
    choices: ["(-√3/2, -1/2)","(√3/2, 1/2)","(-√2/2, -√2/2)","(√2/2, √2/2)"],
    correct: "(-√2/2, -√2/2)"
},
{
    "question": "What are the coordinates of 2π/3?",
    choices: ["(1/2, √3/2)","(-1/2, √3/2)","(-√2/2, √2/2)","(√2/2, √2/2)"],
    correct: "(-1/2, √3/2)"
},
{
    "question": "What's the angle at 5π/3?",
    choices: ["270°","330°","300°","315°"],
    correct: "300°"
},
])
```

Because of `v-model`, I'm able to compare the `:value` of `userChoice` to the correct answer choice listed in my reactive array, in order to enable the corresponding bodies of code. My reactive array is also seen in the above code for a reference.

Next, the concepts of Vue transitions, CSS transitions, and `setTimeout()` are all interconnected in which I use them all together. Here's the direct snippet:

```html
<button class="btn text-dark poppins-regular" @click="checkAnswer()">Submit</button>
<Transition name="correct">
    <img src="/hachi-cheeky-sprite.png" alt="cheeky hachiware" class="icon" v-if="correct" :key="questionNumber">
</Transition>
<Transition name="wrong">
    <img src="/hachi-sad-sprite.png" alt="sad hachiware" class="icon" v-if="wrong" :key="questionNumber">
</Transition>
```

Also following the code snippet from earlier, this HTML is directly connected to my JS function, `checkAnswer` (this is how `setTimeout()` is connected). 

For Vue transitions, the `<Transition>` tags are there to indicate it's a Vue transition. Within the transitions, I made it so that an image of a hachiware sprite would appear (which varies whether the answer is wrong or right). This connects to my CSS transitions now, where I went back to review SEP10 content to get the sprite to ease into the frame:

```css
.correct-enter-active, .correct-leave-active, .wrong-enter-active, .wrong-leave-active {
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.correct-enter-from, .correct-leave-to, .wrong-enter-from, .wrong-leave-to {
  opacity: 0;
  transform: translateY(20px);
}
```

As said earlier, when either transition is active, opacity and transform will ease in. Additionally, when the sprite enters the screen or leaves, there will be a translation horizontally. 

However, in order for the animation to be reapplied each time, I used `setTimeout()`. Here's the specific code snippet within my `checkAnswer()` function.

```js
// after set time set the value of correct back to false for the css transition animation
setTimeout(function(){
    correct.value = false
}, 900);
```

There's another version of this whenever `wrong.value = true`, but in this case, when the user gets a question right, then after 900 milliseconds, `correct` will be set back to false until it becomes true again (through other means). This allows the animation to only play for a set amount of time, as it will hide after. `:key="questionNumber` is also incorporated here, in which it allows the animation to replay per question. So when the question number changes, the animation still works.

Here is a demonstration of both sprite animations:

<img width="800" height="495" alt="2026-04-1818-09-33-ezgif com-video-to-gif-converter" src="https://github.com/user-attachments/assets/a9bd8c01-e770-4f91-aa61-39bbd4c40fce" />

Lastly, I used `sort()` to help me randomize the position of the answer choices for each question. As seen below:

```js
questionaire.value.forEach(function(q){
    // randomize choices using .sort() but instead of comparing actual values, use random
    q.choices.sort(function(){
        return Math.random() - 0.5
    });
    // 5050 chance to get a negative number, hence subtraction
});
```

This will sort the different values of my choices property within my array of questions by reordering the indexes with `Math.random()`. So every time a question is loaded, the order in which the choices appear will be different every time. 

Of course, everything comes together in the full version of my [SEP11 freedom project](https://joleel3389.github.io/sep11-freedom-project/), which you can preview below or by the hidden link:

<img width="800" height="480" alt="ezgif com-video-to-gif-converter (1)" src="https://github.com/user-attachments/assets/8cf3f602-d650-4813-9c43-4de1f9102ab2" />

### Engineering Design Process

---

In my previous blog, I was on step 4 of the Engineering Design Process (EDP). Now, I'm on the 5th and 6th steps of EDP, which are to create a prototype as well as to test and evaluate the prototype. I've finished creating the MVP of my project, and I tested that my website was fully functioning. I applied many of the Vue.js concepts I wanted to from my 4th blog, like `vue-if`, `v-model`, and more. By my next blog, hopefully I can move on to beyond MVP with step 7: to improve as needed.

### Skills

---

Below are the skills I've learned while working on my blog.
* How to read
    * For my tool Vue.js, there were specific concepts I wanted to know after my last blog, but I couldn't find those concepts on [Scrimba](https://scrimba.com/) (the website with interactive videos that I used to learn Vue.js in the beginning). So, I decided to go to the official Vue.js documentation instead to see how some concepts I used on my site like `v-if`, `v-model`, `:key` or Vue transitions. Not only for Vue, but I also used some documentations to review CSS transitions and JS concepts I haven't learned. Even though there was no practice to go with the documentations like I did in my videos, I was still able to analyze and observe how the concepts were being used and also visualize in my head how I would use them.
* Creativity
    * For my project, I also had to consider the design of the website. I wanted to ensure my code was functioning first, so for my MVP I planned the design last. When I was planning the design for my project, I ensured that it wasn't too flashy to take away from the studying element but that it was cute and casual in a way that it'll still catch your attention. I used hachiware—a favorite character of mine—to help make the website appealing, and I'm really proud of the result.

### Next steps

---

For my next steps, I want to move on to step 7 of EDP: to improve as needed. If I have the time, I want to take it to work on my beyond MVP for greater optimization of my freedom project, such as more decks. 

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
