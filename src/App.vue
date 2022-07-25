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
      ],
      results: [
        {
          min: 0,
          max: 2,
          title: "Try again!",
          desc: "Do a little more studying and you may succeed!",
        },
        {
          min: 3,
          max: 3,
          title: "Wow, you're a genius!",
          desc: "Studying has definitely paid off for you!",
        },
      ],
    };
  },
};
</script>
