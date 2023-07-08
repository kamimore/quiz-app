<template>
  <div class="mt-3 d-flex align-items-center justify-content-center">
    <button
      type="button"
      @click="$emit('selected-operator', '+')"
      class="btn btn-success mx-2 p-4 font-weight-bold text-white fs-3"
    >
      Addition
    </button>
    <button
      type="button"
      @click="$emit('selected-operator', '-')"
      class="btn btn-warning mx-2 p-4 font-weight-bold text-white fs-3"
    >
      Subtraction
    </button>
    <button
      type="button"
      @click="$emit('selected-operator', '/')"
      class="btn btn-danger mx-2 p-4 font-weight-bold text-white fs-3"
    >
      Division
    </button>
    <button
      type="button"
      @click="$emit('selected-operator', '*')"
      class="btn btn-primary mx-2 p-4 font-weight-bold text-white fs-3"
    >
      Multiplication
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
