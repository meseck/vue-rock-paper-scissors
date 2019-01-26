<template>
  <div class="container"><h1 class="msg msg--sliding" v-text="msg"></h1></div>
</template>

<script>
export default {
  name: "LoadingText",
  props: {
    msg: {
      type: String,
      required: true
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-content: center;
  background: black;
}
.msg {
  color: white;
  &--sliding {
    animation: slide 5s infinite ease-in-out;
  }
}

@keyframes slide {
  0% {
    transform: translateX(-100%) skewX(20deg);
  }
  20% {
    transform: translateX(0%) skewX(-20deg);
    text-shadow: 0 0 0 rgba(255, 255, 255, 1);
  }
  80% {
    transform: translateX(0%) skewX(-20deg);
    text-shadow: 0 0 0 rgba(255, 255, 255, 1);
  }
  100% {
    transform: translateX(100%) skewX(20deg);
  }
}
</style>
