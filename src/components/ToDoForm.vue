<script>
export default {
  methods: {
    onSubmit() {
      if (this.label.length < 1) return;
      this.$emit("todo-added", this.label);
      this.label = "";
    },
  },
  data: function () {
    return {
      label: "",
    };
  },
};
</script>

<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input"> What needs to be done? </label>
    <input
      type="text"
      id="new-todo-input"
      name="new-todo"
      autocomplete="off"
      v-model.lazy.trim="label"
    />
    <button type="submit">Add</button>
  </form>
</template>
