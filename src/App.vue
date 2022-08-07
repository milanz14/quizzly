<template>
  <div class="ctr">
    <h2>Quizzly!</h2>
    <QuestionsComponent
      v-if="numAnswered < questions.length"
      :numAnswered="numAnswered"
      :questions="questions"
      @updateResult="updateResult"
      @updateActiveQuestion="updateActiveQuestion"
    />
    <ResultComponent v-else :results="results" :result="result" />
    <button type="button" class="reset-btn" @click="resetGame">Reset</button>
  </div>
</template>

<script>
import ResultComponent from "@/components/ResultComponent.vue";
import QuestionsComponent from "@/components/QuestionsComponent.vue";

export default {
  name: "App",
  components: {
    ResultComponent,
    QuestionsComponent,
  },
  methods: {
    updateResult(num) {
      this.result += num;
    },
    updateActiveQuestion() {
      this.numAnswered += 1;
    },
    resetGame() {
      this.numAnswered = 0;
      this.result = 0;
    },
  },
  data() {
    return {
      numAnswered: 0,
      result: 0,
      questions: [
        {
          q: "Who was the legendary Benedictine monk who invented champagne?",
          answers: [
            {
              text: "Dom Pérignon",
              isCorrect: true,
            },
            {
              text: "El Chapo",
              isCorrect: false,
            },
            {
              text: "Benedict of Nursia",
              isCorrect: false,
            },
            {
              text: "Claude Moet",
              isCorrect: false,
            },
          ],
        },
        {
          q: "What is the largest freshwater lake in the world?",
          answers: [
            {
              text: "Lake Superior",
              isCorrect: true,
            },
            {
              text: "Lake Michigan",
              isCorrect: false,
            },
            {
              text: "Caspain Sea",
              isCorrect: false,
            },
            {
              text: "Lake Victoria",
              isCorrect: false,
            },
          ],
        },
        {
          q: "Where would one find the Sea of Tranquility?",
          answers: [
            {
              text: "North Pole",
              isCorrect: true,
            },
            {
              text: "Europe",
              isCorrect: false,
            },
            {
              text: "The Moon",
              isCorrect: true,
            },
            {
              text: "South America",
              isCorrect: false,
            },
          ],
        },
        {
          q: "What country is home to the Cresta Run?",
          answers: [
            {
              text: "USA",
              isCorrect: false,
            },
            {
              text: "Sweden",
              isCorrect: false,
            },
            {
              text: "Australia",
              isCorrect: false,
            },
            {
              text: "Switzerland",
              isCorrect: true,
            },
          ],
        },
        {
          q: "What is someone who shoes horses called?",
          answers: [
            {
              text: "Blacksmith",
              isCorrect: false,
            },
            {
              text: "Farrier",
              isCorrect: true,
            },
            {
              text: "Shoemaker",
              isCorrect: false,
            },
          ],
        },
        {
          q: "Who invented the rabies vaccine?",
          answers: [
            {
              text: "Louis Pasteur",
              isCorrect: true,
            },
            {
              text: "Charles De Gaulle",
              isCorrect: true,
            },
            {
              text: "Gilles Villeneuve",
              isCorrect: false,
            },
          ],
        },
        {
          q: "What is the world's longest river?",
          answers: [
            {
              text: "Amazon",
              isCorrect: false,
            },
            {
              text: "Mississippi",
              isCorrect: false,
            },
            {
              text: "Nile",
              isCorrect: true,
            },
            {
              text: "Danube",
              isCorrect: false,
            },
          ],
        },
        {
          q: "What is the world's largest Ocean?",
          answers: [
            {
              text: "Indian Ocean",
              isCorrect: false,
            },
            {
              text: "Atlantic Ocean",
              isCorrect: false,
            },
            {
              text: "Black Sea",
              isCorrect: false,
            },
            {
              text: "Pacific Ocean",
              isCorrect: true,
            },
          ],
        },
        {
          q: "How many times did Björn Borg win the men's tennis singles title at Wimbledon?",
          answers: [
            {
              text: "1",
              isCorrect: false,
            },
            {
              text: "3",
              isCorrect: false,
            },
            {
              text: "5",
              isCorrect: true,
            },
            {
              text: "7",
              isCorrect: false,
            },
          ],
        },
        {
          q: "What actor starred in 142 films including 'The Quiet Man', 'The Shootiest', 'The Searchers' and 'Stagecoach'?",
          answers: [
            {
              text: "John Wilkes Booth",
              isCorrect: false,
            },
            {
              text: "John Wayne",
              isCorrect: true,
            },
            {
              text: "John Denver",
              isCorrect: false,
            },
            {
              text: "John Cleese",
              isCorrect: false,
            },
          ],
        },
        {
          q: "What color jersey is worn by the winners of each stage of the Tour de Fance?",
          answers: [
            {
              text: "Blue",
              isCorrect: false,
            },
            {
              text: "Green",
              isCorrect: false,
            },
            {
              text: "Orange",
              isCorrect: false,
            },
            {
              text: "Yellow",
              isCorrect: true,
            },
          ],
        },
        {
          q: "Which heavyweight boxing champion was the only one to finish his career of 49 fights without ever being defeated?",
          answers: [
            {
              text: "Evander Holyfield",
              isCorrect: false,
            },
            {
              text: "Mike Tyson",
              isCorrect: false,
            },
            {
              text: "Lennox Lewis",
              isCorrect: false,
            },
            {
              text: "Rocky Marciano",
              isCorrect: true,
            },
          ],
        },
        {
          q: "Which chess piece can only move diagonally?",
          answers: [
            {
              text: "Bishop",
              isCorrect: true,
            },
            {
              text: "Knight",
              isCorrect: false,
            },
            {
              text: "Rook",
              isCorrect: false,
            },
            {
              text: "Queen",
              isCorrect: false,
            },
          ],
        },
        {
          q: "How many valves does a trumpet have?",
          answers: [
            {
              text: "2",
              isCorrect: false,
            },
            {
              text: "3",
              isCorrect: true,
            },
            {
              text: "4",
              isCorrect: false,
            },
            {
              text: "5",
              isCorrect: false,
            },
          ],
        },
        {
          q: "What color is absynthe?",
          answers: [
            {
              text: "blue",
              isCorrect: false,
            },
            {
              text: "yellow",
              isCorrect: false,
            },
            {
              text: "green",
              isCorrect: true,
            },
            {
              text: "purple",
              isCorrect: false,
            },
          ],
        },
      ],
      results: [
        {
          title: "Try again!",
          desc: "Do a little more studying and you may succeed!",
        },
        {
          title: "Wow, you're a genius!",
          desc: "Studying has definitely paid off for you!",
        },
      ],
    };
  },
};
</script>
