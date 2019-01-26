<template>
  <div class="container">
    <div class="randomHandEmoji" v-text="robotHand"></div>

    <LoadingText v-bind:msg="compareHands" />

    <div class="emojiHandBtn-container">
      <emojiHandBtn v-bind:onClick="randomHand" v-bind:emoji="'✋'" />
      <emojiHandBtn v-bind:onClick="randomHand" v-bind:emoji="'✊'" />
      <emojiHandBtn v-bind:onClick="randomHand" v-bind:emoji="'✌️'" />
    </div>
  </div>
</template>

<script>
import EmojiHandBtn from './EmojiHandBtn';
import LoadingText from './LoadingText';

export default {
  components: {
    EmojiHandBtn,
    LoadingText
  },
  data() {
    return {
      msg: 'compareHands',
      robotHand: '🤖',
      humanHand: ''
    };
  },
  methods: {
    randomHand(emoji) {
      const emojiHands = ['✋', '✊', '✌️'];

      function getRandomInt(min, max) {
        min = Math.ceil(min);
        max = Math.floor(max);
        return Math.floor(Math.random() * (max - min)) + min;
      }

      /*       const handsInterval = setInterval(() => { */
      this.robotHand = emojiHands[getRandomInt(0, 3)];
      /*       }, 50); */

      this.humanHand = emoji;

      const msgs = ['Schnick', 'Schnack', 'Schnuck'];
      let counter = 0;

      /* const messagePlay = setInterval(() => {
        if(counter < 3) {
        this.msg = msgs[counter];
        counter++
        }
      }, 250); */
    }
  },
  computed: {
    compareHands() {
      if (this.humanHand === this.robotHand) {
        return 'Draw!';
      } else if (this.humanHand === '✋' && this.robotHand === '✌️') {
        return 'You Loose!';
      } else if (this.humanHand === '✋' && this.robotHand === '✊') {
        return 'You Win!';
      } else if (this.humanHand === '✌️' && this.robotHand === '✊') {
        return 'You Loose!';
      } else if (this.humanHand === '✌️' && this.robotHand === '✋') {
        return 'You Win!';
      } else if (this.humanHand === '✊' && this.robotHand === '✋') {
        return 'You Loose!';
      } else if (this.humanHand === '✊' && this.robotHand === '✌️') {
        return 'You Win!';
      } else if (this.robotHand === '🤖') {
        return 'Choose Hand to start!';
      } else {
        return 'Ähm... something went wrong.';
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-content: center;
  flex-direction: column;
}
.emojiHandBtn-container {
  display: flex;
  justify-content: center;
  align-content: center;
  flex-direction: row;
}
.randomHandEmoji {
  font-size: 80px;
}
</style>
