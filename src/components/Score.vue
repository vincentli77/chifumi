<template>
  <div class="main">
    <div class="container">
        <img class="logo" src="../assets/logo.svg">
        <div class="score">
          <p>SCORE</p>
          <span>12</span>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Score',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .main{
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .container{
    width : 680px;
    height : 145px;
    border: 2px solid  #5A6A84;
    border-radius: 20px;
    margin-top: 2px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding-left: 2%;
    padding-right: 2%;
  }



  .score{
    width: 150px;
    height: 100px;
    background-color: white;
    color: #475596;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    font-weight: bolder;
    border-radius: 10px;
  }
  span{
    color: #545066;
    font-size: 50px;
    font-weight: bold;
  }
</style>
