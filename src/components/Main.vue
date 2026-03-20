<script setup>
    import {ref} from 'vue'
    const questionaire = ref([
    {
        "question": "What's the angle at 3π/4?",
        choices: ["175°","150°","135°","120°"]
    },
    {
        "question": "What's the angle jump at every π/4th of a jump?",
        choices: ["45°","25°","30°","60°"]
    },
    {
        "question": "What are the coordinates of 11π/6?",
        choices: ["(√3/2, -1/2)","(√3/2, 1/2)","(√2/2, -√2/2)","(√2/2, √2/2)"]
    },
    {
        "question": "What's the angle at 7π/6?",
        choices: ["240°","210°","180°","225°"]
    },
    {
        "question": "What's the angle jump at every π/6th?",
        choices: ["30°","60°","90°","15°"]
    },
    {
        "question": "What's the angle jump at every π/2th?",
        choices: ["30°","60°","90°","15°"]
    },
    {
        "question": "What's the angle jump at every π/3th?",
        choices: ["30°","60°","90°","15°"]
    },
    {
        "question": "What are the coordinates of 5π/4?",
        choices: ["(-√3/2, -1/2)","(√3/2, 1/2)","(-√2/2, -√2/2)","(√2/2, √2/2)"]
    },
    {
        "question": "What are the coordinates of 2π/3?",
        choices: ["(1/2, √3/2)","(-1/2, √3/2)","(-√2/2, √2/2)","(√2/2, √2/2)"]
    },
    {
        "question": "What's the angle at 5π/3?",
        choices: ["270°","330°","300°","315°"]
    },
    ])
</script>

<template>
    <div class="container-fluid">
        <div class="container" id="#questionaire">
        <h2 class="text-dark">{{questionaire[0].question}}</h2>
        <input type="radio" name="mcq" value="1" id="Option1"> {{questionaire[0].choices[0]}} <br>
        <input type="radio" name="mcq" value="2" id="Option2"> {{questionaire[0].choices[1]}} <br>
        <input type="radio" name="mcq" value="3" id="Option3"> {{questionaire[0].choices[2]}} <br>
        <input type="radio" name="mcq" value="4" id="Option4"> {{questionaire[0].choices[3]}} <br>
        <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->

        <br>
        <button>Submit</button>
        <br>
        <p></p>
        </div>
    </div>
</template>

<style scoped>
</style>