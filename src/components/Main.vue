<script setup>
    const questionNumber = ref(0);
    const userChoice = ref();
    const correct = ref(false);
    const wrong = ref(false);
    const play = ref(false);
    const done= ref(false);
    const score = ref(0);

    

    function checkAnswer(){
        if(userChoice.value === questionaire.value[questionNumber.value].correct){
            correct.value = true;
            wrong.value = false;
            score.value++;
            questionNumber.value++;
            userChoice.value = undefined;
            // after set time set the value of correct & wrong back to false for the css transition animation
            setTimeout(() => {
                correct.value = false
            }, 900)
            if(questionNumber.value === 10){
                done.value = true;
            }
        } else {
            correct.value = false;
            wrong.value = true;
            // after set time set the value of correct & wrong back to false for the css transition animation
            setTimeout(() => {
                wrong.value = false
            }, 900)
        }
    }

    function refresh(){
        questionNumber.value = 0;
        score.value = 0;
        correct.value = false;
        wrong.value = false;
        userChoice.value = undefined;
        done.value = false;
    }
    
    function home(){
        questionNumber.value = 0;
        score.value = 0;
        correct.value = false;
        wrong.value = false;
        userChoice.value = undefined;
        done.value = false;

        play.value = false;
    }

    function unitCircle(){
        play.value = true;
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
</script>

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
    <div class="container-fluid" id="unitCircle" v-if="!done && play">
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

<style scoped>
</style>