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
        <img class="logo" src="../../src/assets/github.png" />
        <p>GITHUB</p>
      </button>
      <button class="website__button" @click="handleClick(website_url)">
        <svg class="logo" width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path class="logo" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
        </svg>
        <p>WEBSITE</p>
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
    border-radius: 30px;
  }

  .desc, used__technology {
    width: 100%;
  }

  .buttons {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    justify-items: center;

    .github__button, .website__button{
      overflow: hidden;
      background: transparent;
      border-radius: 15px;
      border-color: #FFFFFF;
      border-width: 3px;
      border-style: solid;
      width: 150px;
      height: 60px;

      display: flex;
      flex-direction: row;
      justify-content: space-evenly;
      align-items: center;

      font-family: 'Montserrat', sans-serif;
      font-size: large;
      font-weight: bold;
      text-align: center;
      color: #FFFFFF;
      cursor: pointer;
      z-index: 1;
      position: relative;

      .logo {
        width: 20px;
        height: 20px;
        margin: 0;
        padding: 0;
        z-index: 1;
      }

      p {
        margin: 0;
      }

      &::after {
        content: '';
        z-index: 0;
        position: absolute;
        width: 100%;
        height: 100%;
        background: rgba(225, 225, 225, .5);
        top: 0;
        right: -100%;
        border-radius: 10px;
        transition: .5s ease-out;
      }

      &:hover::after {
        transform: translateX(-100%)
      }
    }
    @media (min-width: 768px) {
      .github__button, .website__button {
        width: 200px;
        height: 100px;

        font-size: 25px;

        .logo {
          width: 30px;
          height: 30px;
        }
      }
    }
  }
}
</style>