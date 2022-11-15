<template>
  <div>
    <p>Reaction timer Game</p>
    <button @click="start" class="playBtn" :disabled="isPlaying">Play</button>
    <div v-if="isPlaying">
      <Block :delay = "delay" />
    </div>
  </div>
</template>

<script>
import Block from './components/Block.vue'
export default {
  name: 'App',
  components : {
    Block,
  },
  data() {
    return {
      isPlaying : false,
      delay:null,
    }
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 1000+ Math.random() * 4000;
    }
  }
}
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
.playBtn {
  cursor: pointer;
  width: 80px;
  background: gray;
  border: none;
  padding: 10px;
  border-radius: 10px;
  color: #000;
  font-weight: bold;
  font-size: 16px;
}
.playBtn:disabled {
  cursor:auto;
  background: darkred;
  color: #fff;
}
</style>
