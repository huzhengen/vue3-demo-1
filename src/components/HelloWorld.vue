<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <button
        v-for="(item, index) in data.players"
        :key="index"
        @click="data.selectPlayer(index)"
      >
        {{ item }}
      </button>
    </div>
    <p>
      The moust favorite player is: <strong>{{ data.favoritePlayer }}</strong>
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";

export default defineComponent({
  name: "HelloWorld",
  props: {
    msg: String,
  },
  setup() {
    const data = reactive({
      players: ["Messi", "Wulei", "Ronaldo"],
      favoritePlayer: "Random",
      selectPlayer: (index: number) => {
        data.favoritePlayer = data.players[index];
      },
    });

    return {
      data,
    };
  },
});
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
