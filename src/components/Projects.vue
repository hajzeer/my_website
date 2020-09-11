<template>
<section class="projects">
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
  <div class="projecst__Inner">
    <img class="perform__photo" :src="photo"/>
    <h2>{{name}}</h2>
    <p class="desc">{{desc}}</p>
    <p class="used__technology"> {{used_tech}}</p>
    <div class="buttons">
      <button class="github__button" @click="handleClick(github_url)">
        GITHUB
      </button>
      <button class="website__button" @click="handleClick(website_url)">
        WEBSITE
      </button>
    </div>
  </div>
</section>
</template>

<script>
export default {
  name: "Projects",

  props: {
    item: {
      type: Object,
    },
  },
  data() {
    return {
      id: this.item.id,
      name: this.item.name,
      photo: this.item.photo,
      github_url: this.item.github_url,
      website_url: this.item.website_url,
      desc: this.item.desc,
      used_tech: this.item.used_tech,

    };
  },
  methods: {
    handleClick(event) {
      window.open(event, '_blank');
    },
  }
}
</script>

<style lang="scss" scoped>

.projects {
  width: 100%;
  height: auto;
  margin-bottom: 30px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .perform__photo {
    width: 90%;
    height: auto;
    border-style: solid;
    padding: 10px;
    border-radius: 20px;
  }

  .desc, used__technology {
    width: 100%;
  }

  .buttons {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;

    .github__button, .website__button{

      background: transparent;
      border-radius: 15px;
      border-color: #FFFFFF;
      border-width: 3px;
      border-style: solid;
      width: 120px;
      height: 60px;

      font-family: 'Montserrat', sans-serif;
      font-size: large;
      font-weight: bold;
      text-align: center;
      color: #FFFFFF;
    }

  }
}
</style>