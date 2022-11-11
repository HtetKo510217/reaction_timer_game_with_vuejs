<template>
  <div>
    <p>Reaction timer Game</p>
    <button @click="start" class="playBtn">Play</button>
    <div v-if="isPlaying">
      <Block />
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
      timer:null,
    }
  },
  methods: {
    start() {
      this.timer = 1000+ Math.random() * 4000;
      setTimeout(()=> {
        this.isPlaying = true;
      },this.timer)
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
  background: darkgray;
  border: none;
  padding: 10px;
  border-radius: 10px;
  color: darkred;
  font-weight: bold;
  font-size: 16px;
}
</style>
