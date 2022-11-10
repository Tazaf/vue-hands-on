<template>
  <img alt="Vue logo" v-bind:title="imgTitle" src="./assets/logo.png" />
  <HelloWorld msg="Foo" v-bind:items="items" />
  <FormComponent />
</template>

<script>
import FormComponent from "./components/FormComponent.vue";
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    FormComponent,
  },
  data: () => {
    return {
      items: ["Foo", "Bar", "Baz", "oiwhefhewf"],
      imgTitle: "Vue logo",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
