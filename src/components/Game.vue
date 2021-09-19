<template lang="fr">
<div @win="win" class="content">
        <div v-if="show" class="top">
            <Circle  type="Papier" url="icon-paper.svg" color="#546FF4" :random='ia.type' @clicked="onClickChild"/>    
        </div>
        <div v-if="show" class="bottom">
            <Circle  type="Pierre" url="icon-rock.svg" color="#EAA116" :random='ia.type' @clicked="onClickChild" />
            <Circle  type="Ciseaux" url="icon-scissors.svg" color="#DE3755" :random='ia.type' @clicked="onClickChild" />
        </div>  
    
        <div v-if="!show" >
            <Battle :player='player' :ia='ia' :result='result' :color='color' :url='url' @restart="restart"/>
        </div>  

</div>



</template>
<script>
import Circle from "../components/Circle";
import Battle from "../components/Battle";

export default {
  name: "Vue",
  components: {
    Circle,
    Battle,
  },

  data() {
    return {
      tab: [
        ["Pierre", "icon-rock.svg", "#EAA116"],
        ["Ciseaux", "icon-scissors.svg", "#DE3755"],
        ["Papier", "icon-paper.svg", "#546FF4"],
      ],
      ia: { color: String, url: String, type: String },
      player: "",
      show: true,
      result: "",
      color: String,
      url: String,
    };
  },

  mounted() {
    this.random();
    console.log(this.ia);
  },
  methods: {
    random: function() {
      const randomElement = this.tab[
        Math.floor(Math.random() * this.tab.length)
      ];
      this.ia.type = randomElement[0];
      this.ia.url = randomElement[1];
      this.ia.color = randomElement[2];
    },
    onClickChild(player, ia, result, color, url) {
      this.show = !this.show;
      this.player = player;
      this.result = result;
      this.color = color;
      this.url = url;
      if (result == "win") {
        this.$emit("win", "win");
      }
    },
    restart() {
      this.show = true;
      this.random();
    },
  },
};
</script>
<style scoped>
.content {
  width: 40vw;
  margin: 0 auto;
  margin-top: 3%;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

.top {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.bottom {
  display: flex;
  justify-content: space-between;
}

/* .fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
} */
</style>
