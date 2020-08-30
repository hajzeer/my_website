<template>
<div class="technical__skills">
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
  <div>
    <img class="skill__logo" :src="photos"/>
    <h2 class="skill__name">{{name}}</h2>
  </div>
</div>
</template>

<script>
export default {
  name: "skills",
  props: {
    item: {
      type: Object,
    }
  },

  data(){
    return{
      id: this.item.id,
      name: this.item.name,
      photo: this.item.photo,
    };
  },
  computed: {
    photos() {
      return `${this.photo}`;
    },
  },
};
</script>

<style scoped lang="scss">

.technical__skills {
  width: 100%;
  font-family: 'Montserrat', sans-serif;
  color: #FFFFFF;
  text-align: center;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50%;

  .skill__logo {
    width: 80px;
    height: 80px;
    margin-bottom: -20px;
  }
}

</style>