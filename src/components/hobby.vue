<template>
<div class="hobby">
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
  <div>
    <img class="hobby__logo" :src="photos"/>
    <h2 class="hobby__name">{{name}}</h2>
  </div>
</div>
</template>

<script>
export default {
name: "hobby",
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
}
</script>

<style scoped lang="scss">

.hobby {
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

  .hobby__logo {
    width: 150px;
    height: 150px;
    margin-bottom: -20px;
  }

  @media (min-width: 768px) {
    .hobby__logo {
      width: 200px;
      height: 200px;
    }
  }
}
</style>