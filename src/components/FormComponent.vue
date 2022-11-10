<template>
  <input
    type="email"
    placeholder="Type in your email"
    name="firstname"
    id="firstname"
    v-model="firstname"
    v-on:input="$emit('firstNameSet', firstname)"
  />
  <button @click="setInputValue()">Set input value</button>
</template>

<script>
export default {
  name: "FormComponent",
  emits: ["firstNameSet"],
  data: () => ({
    firstname: null,
  }),
  methods: {
    setInputValue() {
      this.firstname = "Roxane";
    },
  },
};
</script>
