<template>
  <div>
    <button
      class="btn btn-primary p-4 mx-1 fs-1"
      v-for="(answer, key) in answers"
      @click="selectedAnswer(answer)"
      :key="key"
    >
      {{ answer }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["operator", "leftoperand", "rightoperand"],
  data() {
    return {
      answers: [],
      operations: {
        "+":
          Math.random() * this.leftoperand + Math.random() * this.rightoperand,
        "-":
          Math.random() * this.leftoperand - Math.random() * this.rightoperand,
        "/":
          (Math.random() * this.leftoperand) /
          (Math.random() * this.rightoperand),
        "*":
          Math.random() *
          this.leftoperand *
          (Math.random() * this.rightoperand),
      },
      correctAnswer: {
        "+": this.leftoperand + this.rightoperand,
        "-": this.leftoperand - this.rightoperand,
        "/": this.leftoperand / this.rightoperand,
        "*": this.leftoperand * this.rightoperand,
      },
    };
  },
  mounted() {
    for (let i = 0; i <= 4; i++) {
      let number = parseInt(this.operations[this.operator]);
      while (this.answers.includes(number)) {
        number += parseInt(Math.random() * 11);
      }
      this.answers.push(number);
    }
    let correctAnswer = parseInt(this.correctAnswer[this.operator]);
    if (!this.answers.includes(correctAnswer)) {
      this.answers[Math.floor(Math.random() * this.answers.length)] =
        correctAnswer;
    }
  },
  methods: {
    selectedAnswer(answer) {
      if (answer == parseInt(this.correctAnswer[this.operator])) {
        alert("correct answer");
      } else {
        alert("wrong answer");
      }
    },
  },
};
</script>

<style></style>
