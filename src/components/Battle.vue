<template lang="fr">
<div class="content">
    <Circle  :type="player" :url="url" :color="color" />
    <p class="result">{{result}}</p>
    <Circle  :type="ia.type" :url="ia.url" :color="ia.color" />
</div>
 <button @click="restart" class="restart">Restart</button>
</template>
<script>
import Circle from "../components/Circle";

export default {
  name: "Battle",
  components: {
    Circle,
  },
  props: {
    ia: {},
    player: String,
    result: String,
    url: String,
    color: String,
  },

  data() {
    return {
      style: {
        "--color": this.color,
      },
    };
  },

  methods: {
      restart(){
          this.$emit('restart',false)
      }
  },
};
</script>
<style scoped>
.circle {
  width: 10vw;
  height: 10vw;
  border-radius: 100%;
  border: 2vw solid var(--color);
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: white;
}
.content {
  display: flex;
  align-items: center;
  flex-direction: row !important;
  justify-content: space-between !important;
}
.icon {
  width: 40%;
}

.result {
  font-size: 30px;
  font-weight: bold;
  text-transform: uppercase;
  color: white;
}

.restart {
  width: 100px;
  height: 30px;
  background-color: white;
  color: #475596;
  font-weight: bolder;
  border-radius: 10px;
  cursor: pointer;
}
</style>
