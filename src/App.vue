<template>
  <div id="app"><RandomEmojiHand class="RandomEmojiHand" /></div>
</template>

<script>
import RandomEmojiHand from "./components/RandomEmojiHand";

export default {
  name: "App",
  components: {
    RandomEmojiHand
  }
};
</script>

<style>
body {
  background-color: yellow;
  margin: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
.RandomEmojiHand {
  width: 100%;
}
</style>
