<template>
  <div ref="starter" v-if="visibility" class="starter" @click="toggleClick()">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
    <h1 ref="slogan1" class="open__slogan">CLICK TO ENTER</h1>
    <img ref="starter__photo" class="starter__photo" src="../assets/world_map_.svg" alt="map__starter"/>
    <h1 ref="slogan" class="open__slogan">TO MY WORLD</h1>
  </div>
</template>
<script>
//import WorldMap from './assets/world_map_.svg';
import gsap from 'gsap';

export default {
  name: "starter",
  data(){
    return{
      visibility: true,
    }
  },
  mounted() {
    const {starter__photo, slogan, slogan1} = this.$refs;

    gsap.fromTo(slogan1,
        {opacity: 0},
        {opacity: 1, duration: 1.5, ease: "power4.out", delay: 2});
    gsap.fromTo(starter__photo,
        {opacity: 0, y: -50},
        {opacity: 1, y: 0, duration: 3, ease: "power4.out", delay: .6});
    gsap.fromTo(slogan,
        {opacity: 0},
        {opacity: 1, duration: 1.5, ease: "power4.out", delay: 2});
    gsap.fromTo(starter__photo,
        {y:0},
        {y:20 ,repeat: -1, yoyo:true, duration: 2, delay: 2.5})
  },
  methods: {
    toggleClick()  {
      const {starter, starter__photo} = this.$refs;
      gsap.to(starter,
          {scale:10,opacity: 0, duration: 2});
      gsap.to(starter__photo,
          {x:-25, y: 30, duration: 2});

      setTimeout(function () {
        this.visibility = !this.visibility
      }.bind(this), 3000);
    },
  },
};

</script>


<style scoped lang="scss">

.starter {
  z-index: 1;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100vh;
  background-color: #FFED00;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: fixed;

  .open__slogan {
    font-family: 'Montserrat', sans-serif;
    color: #FFFFFF;
  }
  .starter__photo {
    width: 100%;
    height: auto;
    margin: 0;
    padding: 0;
  }
}

</style>