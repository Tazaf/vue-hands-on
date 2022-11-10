<template>
  <h1>{{ msg }}</h1>
  <h2>{{ title }}</h2>
  <!-- Insérer ici mon composant -->
  <FormComponent v-on:first-name-set="setFirstName" />
  <div v-if="firstNameIsDefined()">
    <p>Bonjour, {{ firstname }}</p>
    <button @click="showFirstname()">Save</button>
  </div>
  <button v-on:click="changeTitleLabel()">Changer le titre</button>
  <ul>
    <li v-for="item of items" :key="item">{{ item }}</li>
  </ul>
</template>

<script>
import FormComponent from "./FormComponent.vue";

let titleCache = "Bonjour Monde";

export default {
  name: "HelloWorld",
  components: { FormComponent },
  props: ["msg", "items"],
  data: () => {
    return {
      title: "Hello World",
      firstname: null,
    };
  },
  methods: {
    changeTitleLabel() {
      let swap = this.title;
      this.title = titleCache;
      titleCache = swap;
    },
    showFirstname() {
      alert(this.firstname);
    },
    setFirstName(firstname) {
      this.firstname = firstname;
    },
    firstNameIsDefined() {
      return this.firstname !== null && this.firstname !== undefined;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
