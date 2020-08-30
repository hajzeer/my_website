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
          work in progress
        <Projects/>
      </div>
      <div class="technical__skills">
        <h1>TECHNICAL SKILLS</h1>
        <div class="resoults">
          <skills
            v-for="item in resoults"
            :item="item"
            :key="item.id"
          />
        </div>
      </div>
      <div class="hobby">
        <h1>HOBBY</h1>
        work in progress
      </div>
      <div class="lang">
        <h1>LANGUAGE</h1>
        <div class="language" v-for="language in languages" :key="language.id">
          <p>{{language.name}}</p>
          <p>{{language.level}}</p>
        </div>
      </div>
      <div class="contact">
        <h1>CONTACT</h1>
        <a href="tel: +48 661 149 308">+48 661 149 308</a>
        <a href="mailto: krzysh98@gmail.com">krzysh98@gmail.com</a>
        <div class="social__media">
          <Contact v-for="item in socialMedias" :key="item.id" :item="item"/>
        </div>
      </div>
      <div class="designer">
        <p>
          © 2020 Krzysztof Hajder
          <br/>
          All rights reserved
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import Starter from "@/components/starter";
import HeroImage from "@/components/HeroImage";
import Projects from "@/components/Projects";
import Skills from "@/components/skills";
import Contact from "@/components/contact";

import js from "./assets/js.png";
import html from "./assets/html.png";
import css from "./assets/css.png";
import scss from "./assets/scss.png";
import vue from "./assets/vue.png";
import react from "./assets/react.png";
import nuxt from "./assets/nuxt.png";
import git from "./assets/git.png";
import csharp from "./assets/csharp.png";
import adobexd from "./assets/adobexd.png";

import github from "./assets/github.png";
import linkedin from "./assets/linkedin.png";
import facebook from "./assets/facebook.png";
import instagram from "./assets/instagram.png";

export default {
  name: 'App',
  components: {
    Starter,
    HeroImage,
    Projects,
    Skills,
    Contact,
  },
  data() {
    return{
      resoults: [
        {id: 0, photo: js, name: "JavaScript"},
        {id: 1, photo: html, name: "HTML5"},
        {id: 2, photo: css, name: "CSS"},
        {id: 3, photo: scss, name: "SCSS"},
        {id: 4, photo: vue, name: "Vue"},
        {id: 5, photo: react, name: "React"},
        {id: 6, photo: nuxt, name: "Nuxt"},
        {id: 7, photo: git, name: "GIT"},
        {id: 8, photo: csharp, name: "C#"},
        {id: 9, photo: adobexd, name: "Adobe XD"},
      ],
      languages: [
        {id: 0, name: "English", level: "Intermediate"},
        {id: 1, name: "Polish", level: "Native"},
      ],
      socialMedias: [
        {id: 0,
          name: "linkedin",
          src_social: linkedin,
          social_link: "https://www.linkedin.com/in/krzysztof-hajder-5270b6182/" },
        {id: 1,
          name: "github",
          src_social: github,
          social_link: "https://github.com/hajzeer"},
        {id: 2,
          name: "facebook",
          src_social: facebook,
          social_link: "https://www.facebook.com/hajzeer"},
        {id: 3,
          name: "instagram",
          src_social: instagram,
          social_link: "https://www.instagram.com/krzysiuhajder/"},
      ],
    };
  },
};
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

    .resoults {
      margin-top: 1em;
      justify-items: center;
      margin-bottom: 20px;
      width: 100%;
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-gap: 15px;
    }

    .language {
      width: 100%;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
    }
    .contact{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      a{
        padding: 20px;
        text-decoration: none;
        color: #FFFFFF;
      }

      .social__media {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
      }
    }
  }
</style>
