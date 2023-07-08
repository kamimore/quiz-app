<template>
  <div
    class="mt-3 d-flex flex-column align-items-center justify-content-center"
  >
    <div class="h1 text-center mt-4">Quiz</div>
    <OperatorComponent v-if="!operator" @selected-operator="SelectedOperator" />
    <SelectedOperator v-else :operator="operator"  @remove-operator="operator = null" />
  </div>
</template>

<script>
import OperatorComponent from "./components/OperatorComponent.vue";
import SelectedOperator from "./components/SelectedOperator.vue";

export default {
  name: "App",
  data() {
    return {
      operator: null,
    };
  },
  methods: {
    SelectedOperator(operator) {
      this.operator = operator;
    },
  },
  components: {
    OperatorComponent,
    SelectedOperator,
  },
};
</script>

<style></style>
