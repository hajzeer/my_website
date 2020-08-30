<template>
  <div class="app">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
    <Starter />
    <div class="wrapper">
      <HeroImage />
    </div>
    <div class="container">
      <div class="main__info">
        <h2 class="slogan">"Strive for Greatness" <br/> LeBron James</h2>
        <h1 class="about_me">ABOUT ME</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur lobortis accumsan mi, et efficitur erat bibendum ut. Curabitur condimentum magna ac nisl accumsan, non eleifend orci vestibulum. Morbi at sem vulputate, iaculis nunc quis, molestie mi. Maecenas volutpat posuere mauris, vitae egestas dolor ultrices non.
        </p>
      </div>
      <div class="my__projects">
        <h1>MY PROJECTS</h1>
      </div>
    </div>
  </div>
</template>

<script>
import Starter from "@/components/starter";
import HeroImage from "@/components/HeroImage";

export default {
  name: 'App',
  components: {
    Starter,
    HeroImage,
  }
}
</script>

<style lang="scss">
  body {
    margin: 0;
    padding: 0;
  }
  .app {
    background: #FFED00;
    width: 100%;
  }
  .wrapper{
    width: 100%;
    height: 100vh;
  }
  .container{
    width: 100vw;
    margin: 0;
    padding: 0;
    top: 0;
    right: 0;
    bottom: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    h1 {
      font-size: 2em;
    }

    font-family: 'Montserrat', sans-serif;
    color: #FFFFFF;
    text-align: center;

    .main__info{
      .slogan{
        font-style: italic;
        font-size: 1.5em;
      }
    }
  }
</style>
