<template>
  <div class="questions-ctr">
    <div class="progress">
      <div class="bar"></div>
      <div class="status">
        {{ numAnswered }} questions answered out of {{ questions.length }}
      </div>
    </div>
    <div
      class="single-question"
      v-for="(question, idx) in questions"
      :key="question.q"
      v-show="numAnswered === idx"
    >
      <div class="question">{{ question.q }}</div>
      <div class="answers" v-for="(answer, idx) in question.answers" :key="idx">
        <div class="answer" @click="selectAnswer(answer.isCorrect)">
          {{ answer.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "QuestionsComponent",
  props: ["questions", "numAnswered"],
  methods: {
    selectAnswer(data) {
      if (data) {
        this.$emit("updateResult", 1);
      }
      this.$emit("updateActiveQuestion");
    },
  },
};
</script>
