<template>
<div class="hero__imageOuter">
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
  <div class="main">
    <h1 ref="main" class="main_text1">IT IS ME</h1>
    <h1 ref="main" class="main_text2">KRZYSZTOF HAJDER</h1>
  </div>
  <div class="hero__imageInner"></div>
</div>
</template>

<script>
export default {
name: "HeroImage"
}
</script>

<style scoped lang="scss">
.hero__imageOuter{
  z-index: -1;
  background: #243a70;
  width: 100%;
  height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .main {
    z-index: 2;
    overflow: hidden;
    border-bottom-left-radius: 30% ;
    border-bottom-right-radius: 30% ;
    box-shadow: 0 0 50rem black;
    background-color: #3254a8;
    width: 100%;
    height: 40%;
    h1 {
      font-family: 'Montserrat', sans-serif;
      color: #FFFFFF;
      text-align: center;
    }
    .main_text1 {
      margin-top: 40px;
      margin-bottom: -20px;
    }
  }

  .hero__imageInner {
    width: 100%;
    height: 70%;
    background-image: url('../../src/assets/HeroImage.svg');
    background-position: 50% 50%;
    background-repeat: no-repeat;
    background-size: cover;
  }
}
</style>