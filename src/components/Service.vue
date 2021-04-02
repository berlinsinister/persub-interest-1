<template>
  <div class="service-container">
    <div>
      <img :src="require('../assets/images/' + url)" alt="service" />
      <div id="border"></div>
      <div id="title">{{ title }}</div>
      <div id="subtitle">
        Bringing family and friends together in support of one another.
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Service",
  props: {
    title: String,
    url: String,
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/vars";
@import "../assets/sass/mixins";

.service-container {
  width: 32rem;
  height: 32rem;
  border-radius: 5rem;
  border: 1px solid #b4b4b4;
  transition: $transition-time ease-out;
  @include flex-centered-totally;
  &:hover {
    cursor: pointer;
    background: #ee7038;
    & img {
      transform: rotate(0);
    }
    & #border {
      display: none;
    }
  }
  & > div {
    width: 27rem;
    height: 27rem;
    border-radius: 3.5rem;
    position: relative;
  }
  & img {
    width: 27rem;
    height: 18rem; // auto;
    max-width: 100%;
    object-fit: cover;
    border-radius: 3.5rem;
    transform: rotate(-2.5deg);
    transition: $transition-time ease-out;
    &:hover {
      filter: brightness(1.1);
    }
  }
  & #border {
    position: absolute;
    top: 0;
    left: 0;
    width: 27rem;
    height: 18rem; // auto;
    border: 1px solid #c6bfaf;
    border-radius: 3.5rem;
  }
  & #title,
  & #subtitle {
    text-align: center;
    margin-top: 1rem;
  }
  & #title {
    font-size: 2rem;
    font-weight: 500;
  }
}
</style>