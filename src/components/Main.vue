<script setup>
    import {ref} from 'vue'

    const deckNumber = ref();
    const questionNumber = ref(0);

    const userChoice = ref();
    const correct = ref(false);
    const wrong = ref(false);
    const done= ref(false);
    const score = ref(0);

    const play = ref(false);

    function checkAnswer(){
        // look into the array, then get the index for current question, then find the correct property
        if(userChoice.value === decks.value[deckNumber.value].questionaire[questionNumber.value].correct){ // ref needs .value in order to access the nested objects/arrays
            correct.value = true;
            wrong.value = false;
            score.value++;
            questionNumber.value++;
            userChoice.value = undefined;
            // after set time set the value of correct back to false for the css transition animation
            setTimeout(function() {
                correct.value = false
            }, 900);
            if(questionNumber.value === decks.value[deckNumber.value].questionaire.length){ // If the user reaches the last question (how long the questionaire array is), allow the deck to be complete
                done.value = true;
            }
        } else {
            correct.value = false;
            wrong.value = true;

            score.value -= 0.5;
            if(score.value < 0){
                score.value = 0;
            }
            
            // after set time set the value of wrong back to false for the css transition animation
            setTimeout(function() {
                wrong.value = false
            }, 900);
        }
    }

    function refresh(){ // reset everything from question number, score, etc.
        questionNumber.value = 0;
        score.value = 0;
        correct.value = false;
        wrong.value = false;
        userChoice.value = undefined;
        done.value = false;
    }
    
    function home(){
        questionNumber.value = 0; // start at the first question
        score.value = 0; // start with no score
        correct.value = false; 
        wrong.value = false;
        userChoice.value = undefined; // reset the user's selected radio button 
        done.value = false;

        play.value = false;
    }

    function unitCircleDeck(){
        play.value = true;
        deckNumber.value = "unitCircle"; // allows the check answer function to check strictly for the deck being used, in this case the unit circle.

        decks.value[deckNumber.value].questionaire.forEach(function(q){
        // randomize choices using .sort() but instead of comparing actual values, use random
        q.choices.sort(function() {
            return Math.random() - 0.5
        });
        // 5050 chance to get a negative number, hence subtraction
    });
    }

    function derivativesDeck(){
        play.value = true;
        deckNumber.value = "derivatives"; // allows the check answer function to check strictly for the deck being used, in this case the unit circle.

        decks.value[deckNumber.value].questionaire.forEach(function(q){
        // randomize choices using .sort() but instead of comparing actual values, use random
        q.choices.sort(function() {
            return Math.random() - 0.5
        });
        // 5050 chance to get a negative number, hence subtraction
    });
    }

    const decks = ref({ // object of decks
        unitCircle: { //unit circle set
            questionaire: [ //question array
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
                }
            ]
        },
        derivatives: { // derivatives set
            questionaire: [ // question array
                {
                    "question": "What is the derivative of sin(x)?",
                    choices: ["cos(x)","-cos(x)","tan(x)","-tan(x)"],
                    correct: "cos(x)"
                },
                {
                    "question": "What's the derivative of cos(x)?",
                    choices: ["csc(x)","-csc(x)","-sin(x)","sin(x)"],
                    correct: "-sin(x)"
                },
                {
                    "question": "What's the derivative of tan(x)?",
                    choices: ["csc²(x)","-csc²(x)","-sec²(x)","sec²(x)"],
                    correct: "sec²(x)"
                },
                {
                    "question": "What's the derivative of csc(x)?",
                    choices: ["-csc(x)cot(x)","csc(x)cot(x)","-sec(x)cot(x)","sec(x)cot(x)"],
                    correct: "-csc(x)cot(x)"
                },
                {
                    "question": "What's the derivative of sec(x)?",
                    choices: ["sec(x)tan(x)","-sec(x)tan(x)","csc(x)tan(x)","-csc(x)tan(x)"],
                    correct: "sec(x)tan(x)"
                },
                {
                    "question": "What's the derivative of cot(x)",
                    choices: ["-csc²(x)","csc²(x)","-cot²(x)","cot²(x)"],
                    correct: "-csc²(x)"
                },
                {
                    "question": "The derivative of ___ is 1/(1+x²)?",
                    choices: ["arctan(x)","arcsin(x)","arccos(x)","tan²(x)"],
                    correct: "arctan(x)"
                },
                {
                    "question": "The derivative of ___ is 1/(√1-x²)?",
                    choices: ["arctan(x)","arcsin(x)","arccos(x)","sin²(x)"],
                    correct: "arcsin(x)"
                }
            ]
        }
    })
</script>

<template>
    <div class="container-fluid" id="home" v-if="!play"> <!-- only if the user is not in play mode -->
        <img src="/hachi-nerd-sprite.png" alt="NERDY hachiware" class="icon">
        <p class="text-light-dark center baloo-2-regular">Choose your deck:</p>
        <div id="buttonAlign">
        <button class="btn text-dark center poppins-regular" @click="unitCircleDeck()">Unit circle</button>
        <button class="btn text-dark center poppins-regular" @click="derivativesDeck()">Derivatives</button>
        </div>
    </div>
    <div class="container-fluid" id="score" v-if="play"> <!-- only if the user is in play mode regardless of deck -->
        <p class="text-light-dark left baloo-2-regular">Score: {{score}}</p>
        <p class="text-light-dark right baloo-2-regular">{{questionNumber}}/{{decks[deckNumber].questionaire.length}}</p>
    </div>
    <div class="container-fluid" id="deck" v-if="!done && play">
        <div class="container" id="questionaire">
            <h2 class="text-dark baloo-2-regular">{{decks[deckNumber].questionaire[questionNumber].question}}</h2>
            <div class="baloo-2-regular" id="bulletPoints">
                <!-- in the template, the ref doesn't need .value -->
                <input type="radio" name="mcq" :value="decks[deckNumber].questionaire[questionNumber].choices[0]" id="Option1" v-model="userChoice"> {{decks[deckNumber].questionaire[questionNumber].choices[0]}} <br>
                <input type="radio" name="mcq" :value="decks[deckNumber].questionaire[questionNumber].choices[1]" id="Option2" v-model="userChoice"> {{decks[deckNumber].questionaire[questionNumber].choices[1]}} <br>
                <input type="radio" name="mcq" :value="decks[deckNumber].questionaire[questionNumber].choices[2]" id="Option3" v-model="userChoice"> {{decks[deckNumber].questionaire[questionNumber].choices[2]}} <br>
                <input type="radio" name="mcq" :value="decks[deckNumber].questionaire[questionNumber].choices[3]" id="Option4" v-model="userChoice"> {{decks[deckNumber].questionaire[questionNumber].choices[3]}} <br>
                <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->
            </div>

            <button class="btn text-dark poppins-regular" @click="checkAnswer()">Submit</button>
            <Transition name="correct"> <!-- if correct answer is selected, trigger happy hachiware animation -->
                <img src="/hachi-cheeky-sprite.png" alt="cheeky hachiware" class="icon" v-if="correct" :key="questionNumber">
            </Transition>
            <Transition name="wrong"> <!-- if wrong answer is selected, trigger sad hachiware animation -->
                <img src="/hachi-sad-sprite.png" alt="sad hachiware" class="icon" v-if="wrong" :key="questionNumber">
            </Transition>
        </div>
    </div>

    <div class="container-fluid" id="complete" v-if="done && play"> // toggles only if the user finishes a deck (within play mode)
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