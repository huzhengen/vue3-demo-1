<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Suspense>
    <template #default>
      <AsyncShow />
    </template>
    <template #fallback>
      <h1>Loading...</h1>
    </template>
  </Suspense>
  <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  <BasicExample />
  <Time />
  <Dog />
  <!-- <Modal /> -->
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import BasicExample from "./components/BasicExample.vue";
import Time from "./components/Time.vue";
import Dog from "./components/Dog.vue";
// import Modal from "./components/Modal.vue";
import AsyncShow from "./components/AsyncShow.vue";

export default defineComponent({
  name: "App",
  components: {
    HelloWorld,
    BasicExample,
    Time,
    Dog,
    // Modal,
    AsyncShow,
  },
});
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
