<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>
      <button
          v-for="(item, index) in players"
          :key="index"
          @click="selectPlayer(index)"
      >
        {{ item }}
      </button>
    </div>
    <p>
      The moust favorite player is: <strong>{{ favoritePlayer }}</strong>
    </p>
  </div>
</template>

<script lang="ts">
import {defineComponent, reactive, toRefs, watch} from "vue";

interface DataProps {
  players: string[];
  favoritePlayer: string;
  selectPlayer: (index: number) => void;
}

export default defineComponent({
  name: "HelloWorld",
  props: {
    msg: String,
  },
  setup() {
    const data: DataProps = reactive({
      players: ["Messi", "Wulei", "Ronaldo"],
      favoritePlayer: "Random",
      selectPlayer: (index: number) => {
        data.favoritePlayer = data.players[index];
      },
    });

    const refData = toRefs(data);

    watch(refData.favoritePlayer, (newValue) => {
      document.title = newValue;
    });

    return {
      ...refData,
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
