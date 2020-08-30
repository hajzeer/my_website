<template>
<div class="contact">
  <button class="social__media__button" @click="handleClick()">
    <img class="social__media__logo" :src="src_social" />
  </button>
</div>
</template>

<script>
export default {
  name: "contact",
  props: {
    item: {
      type: Object,
    },
  },
  data() {
    return{
      id: this.item.id,
      name: this.item.name,
      src_social: this.item.src_social,
      social_link: this.item.social_link,
    };
  },
  methods: {
    handleClick() {
      window.open(this.item.social_link, '_blank');
    },
  }
};
</script>

<style scoped lang="scss">
.contact {
  width: 100%;

  .social__media__button {
    margin: 10px;
    width: 50px;
    height: 50px;
    background-color: transparent;
    border: none;
    cursor: pointer;


    .social__media__logo {
      width: 100%;
      height: auto;
    }
  }
}

</style>