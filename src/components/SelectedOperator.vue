<template>
  <div>
    <div v-if="startQuiz">
      <div class="d-flex flex-row align-items-center justify-content-center">
        <div
          class="btn btn-info mx-1 my-4 text-white fs-4 px-4 font-weight-bolder"
        >
          {{ leftoperand }}
        </div>
        <div
          class="btn btn-info mx-1 my-4 text-white fs-4 px-4 font-weight-bolder"
        >
          {{ operator }}
        </div>
        <div
          class="btn btn-info mx-1 my-4 text-white fs-4 px-4 font-weight-bolder"
        >
          {{ rightoperand }}
        </div>
      </div>
      <QuizComponent
        :operator="operator"
        :leftoperand="leftoperand"
        :rightoperand="rightoperand"
      />
    </div>
    <div class="mt-3 d-flex align-items-center justify-content-center">
      <button v-if="!startQuiz"
        type="button"
        class="btn btn-success mx-2 p-4 font-weight-bold text-white fs-3"
        @click="startQuiz = true"
      >
        Start
      </button>
      <button
        type="button"
        @click="$emit('remove-operator', null)"
        class="btn btn-warning mx-2 p-4 font-weight-bold text-white fs-3"
      >
        Back
      </button>
    </div>
  </div>
</template>
<script>
import QuizComponent from "./QuizComponent.vue";
export default {
  data() {
    return {
      leftoperand: parseInt(Math.random() * 33),
      rightoperand: parseInt(Math.random() * 11),
      startQuiz: false,
    };
  },
  props: ["operator"],
  components: {
    QuizComponent,
  },
};
</script>

<style scoped></style>
