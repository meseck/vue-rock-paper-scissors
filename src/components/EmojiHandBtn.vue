<template>
  <div v-on:click="onClick(emoji)" v-text="emoji"></div>
</template>

<script>
export default {
  name: 'EmojiHandBtn',
  props: {
    onClick: {
      type: Function,
      required: true
    },
    emoji: {
      type: String,
      required: true
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  padding: 20px;
  font-size: 80px;
  cursor: pointer;
}
</style>
