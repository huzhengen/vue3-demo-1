<template>
  <div v-if="loading">Loading.....</div>
  <img v-if="loaded" :src="result.message" alt="dog"/>
  <div></div>
  <hr>
</template>

<script>
import useUrlAxios from "../hooks/useUrlAxios";

export default {
  name: "Dog",
  setup() {
    const {result, loading, loaded} = useUrlAxios(
        "https://dog.ceo/api/breeds/image/random"
    );

    return {result, loading, loaded};
  },
};
</script>
