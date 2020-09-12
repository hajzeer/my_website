<template>
  <div class="app">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,400;0,700;1,300&display=swap" rel="stylesheet">
    <Starter />
    <div class="wrapper">
      <HeroImage />
    </div>
    <div ref="container" class="container">
      <section class="main__info">
        <h2 class="slogan">"Strive for Greatness" <br/> LeBron James</h2>
        <h1 class="about_me">ABOUT ME</h1>
        <p class="main__desc">
          I am a full of zeal, front-end developer.
          My journey with programming started many of years ago and
          it was a long path to find main topic in programming.
          <br/>
          Nowadays I am a student of computer science and freelance developer.
          <br/><br/>
          <span>
            If you are interested in co-op to design and create
            website for you or your business,
          </span>
          <br/><br/>
            Write to me DM now!
          <br/>
          My previous projects are below.
          Links to contact are on the bottom of the site
        </p>
      </section>
      <section class="my__projects">
        <h1>MY PROJECTS</h1>
        <section>
          <Projects
            v-for="item in projects"
            :item="item"
            :key="item.id"
          />
        </section>
      </section>
      <section class="technical__skills">
        <h1>TECHNICAL SKILLS</h1>
        <section class="resoults">
          <skills
            v-for="item in resoults"
            :item="item"
            :key="item.id"
          />
        </section>
      </section>
      <section class="hobby">
        <h1>HOBBY</h1>
        <section class="resoults">
          <hobby
            v-for="item in hobbies"
            :item="item"
            :key="item.id"
          />
        </section>
      </section>
      <section class="lang">
        <h1>LANGUAGE</h1>
        <section class="language" v-for="language in languages" :key="language.id">
          <p>{{language.name}}</p>
          <p>{{language.level}}</p>
        </section>
      </section>
      <section class="contact">
        <h1>CONTACT</h1>
        <img class="social__media__photo" src="./assets/social_media.svg" alt="social__media__photo"/>
        <a href="mailto: krzysh98@gmail.com">krzysh98@gmail.com</a>
        <div class="social__media">
          <Contact v-for="item in socialMedias" :key="item.id" :item="item"/>
        </div>
      </section>
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
import gsap from 'gsap';
import {ScrollTrigger} from  'gsap/ScrollTrigger';

import Starter from "@/components/starter";
import HeroImage from "@/components/HeroImage";
import Projects from "@/components/Projects";
import Skills from "@/components/skills";
import Contact from "@/components/contact";
import Hobby from "@/components/hobby";

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
import gsapLogo from "./assets/gsap.svg";

import github from "./assets/github.png";
import linkedin from "./assets/linkedin.png";
import facebook from "./assets/facebook.png";
import instagram from "./assets/instagram.png";

import basketball from "./assets/basketball.svg";
import travel from "./assets/travel.svg";
import programming from "./assets/programming.svg";
import cosmos from "./assets/cosmos.svg";
import technology from "./assets/tech.svg";
import books from "./assets/books.svg";

import srebrnacma from "./assets/srebrnacma.png";
import autoserwis from "./assets/autoserwis.png";
import coda from './assets/grupacoda.png';

export default {
  name: 'App',
  components: {
    Starter,
    HeroImage,
    Projects,
    Skills,
    Contact,
    Hobby,
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
        {id: 10, photo: gsapLogo, name: "GSAP"},
      ],
      languages: [
        {id: 0, name: "English", level: "B2"},
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
      hobbies: [
        {id: 0, name: "Traveling", photo: travel},
        {id: 1, name: "Coding", photo: programming},
        {id: 2, name: "Basketball", photo: basketball},
        {id: 3, name: "Astronomy", photo: cosmos},
        {id: 4, name: "Technology", photo: technology},
        {id: 5, name: "Books", photo: books},

      ],
      projects: [
        {id: 0,
          name: "Srebrna Ćma Tattoo Studio",
          photo: srebrnacma,
          github_url: "https://github.com/hajzeer/srebrna_cma_tattoostudio",
          website_url: "https://srebrnacma.pl/",
          desc: "Website to perform work of Tattoo Studio",
          used_tech: "Used: Vue, Instagram API",
        },
        {
          id: 1,
          name: "Autoserwis-lakiernictwo",
          photo: autoserwis,
          github_url: "https://github.com/hajzeer/autoserwis-vue-app",
          website_url: "https://autoserwis-lakiernictwo.pl/#/",
          desc: "This website was created for autoserwis paintshop, " +
              "to present work and services for potentional costumer",
          used_tech: "Used: Vue, link-router",
        },
        {
          id: 2,
          name: "Grupa CODA",
          photo: coda,
          github_url: "https://github.com/hajzeer/CODA_web_2_react",
          website_url: "https://grupacoda.pl/",
          desc: "Presentation of company's services for " +
              "potentional constumers",
          used_tech: "Used: React",
        },
      ],
    };
  },
  mounted() {
    gsap.registerPlugin(ScrollTrigger);

    const sections = document.querySelectorAll('section');

    sections.forEach(section => {
      gsap.fromTo(section.children,
          {y: '+=100', opacity: 0},
          {y: 0, opacity: 1, stagger: 0.2, duration: 1, ease: 'easeInOut',
            scrollTrigger: {
              trigger: section,
              start: 'top 65%',
          }});
    });
  },
};
</script>

<style lang="scss">
  body {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  .app {
    background: #3254a8;
    width: 100%;
  }
  .wrapper{
    width: 100%;
    height: 100vh;
  }
  .container{
    z-index: 999;
    width: 100%;
    margin: 0;
    padding: 0;
    top: 0;
    right: 0;
    bottom: 0;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;


    font-family: 'Montserrat', sans-serif;
    color: #FFFFFF;
    text-align: center;

    p {
      font-size: 20px;

      span {
        font-weight: bolder;
      }
    }

    .main__desc {
      padding: 20px;
    }
    h1 {
      font-size: 2em;
    }

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
        cursor: pointer;
        padding: 20px;
        text-decoration: none;
        font-size: 20px;
        color: #FFFFFF;
      }

      .social__media {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
      }
    }

    @media (min-width: 768px) {
      .resoults {
        grid-template-columns: 1fr 1fr 1fr;
        grid-gap: 30px;
      }

      h1 {
        font-size: 3em;
      }

      h2 {
        font-size: 2em;
      }

      p {
        font-size: 30px;
      }
      .contact {
        a {
          font-size: 30px;
        }
      }
    }

    @media (min-width: 1024px) {
      .resoults {
        grid-template-columns: 1fr 1fr 1fr 1fr;
        grid-gap: 100px;
      }
    }
  }
</style>
