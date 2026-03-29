<script setup>
    const questionNumber = ref(0);
    const userChoice = ref();
    const correct = ref(false);
    const wrong = ref(false);

    function checkAnswer(){
        if(userChoice.value === questionaire.value[questionNumber.value].correct){
        correct.value = true;
        wrong.value = false;
        questionNumber.value++;
        } else {
        wrong.value = true;
        correct.value = false;
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
        choices: ["(√3/2, -1/2)","(√3/2, 1/2)","(√2/2, -√2/2)","(√2/2, √2/2)"],
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
</script>

<template>
    <div class="container-fluid">
        <div class="container" id="#questionaire">
        <h2 class="text-dark">{{questionaire[questionNumber].question}}</h2>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[0]" id="Option1" v-model="userChoice"> {{questionaire[questionNumber].choices[0]}} <br>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[1]" id="Option2" v-model="userChoice"> {{questionaire[questionNumber].choices[1]}} <br>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[2]" id="Option3" v-model="userChoice"> {{questionaire[questionNumber].choices[2]}} <br>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[3]" id="Option4" v-model="userChoice"> {{questionaire[questionNumber].choices[3]}} <br>
        <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->

        <br>
        <button class="btn btn-secondary" @click="checkAnswer()">Submit</button>
        <br>
        <p v-if="correct">Correct!</p>
        <p v-else-if="wrong">Incorrect! Try again.</p>
        </div>
    </div>
</template>

<style scoped>
</style>