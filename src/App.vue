<template>
  <Score :wine="this.wine" msg="Welcome to Your Vue.js App"/>
  <Game @win="win"/>
</template>

<script>
import Score from './components/Score.vue'
import Game from './components/Game.vue'

export default {
  name: 'App',
  components: {
    Score,
    Game
  },
    methods: {
    win(){
      this.wine=this.wine+1
      
    }
  },
  data() {
    return {
      wine: 0
    }
  },


}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}

html,body {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #1A2749;
  height: 100%;

}
</style>
