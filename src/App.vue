<template>
  <Score msg="Welcome to Your Vue.js App"/>
  <Game/>
</template>

<script>
import Score from './components/Score.vue'
import Game from './components/Game.vue'

export default {
  name: 'App',
  components: {
    Score,
    Game
  }
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
