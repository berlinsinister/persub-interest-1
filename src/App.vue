<template>
  <Header />
  <main>
    <div class="goals">
      <p id="title">What's your interest?</p>
    </div>
    <div class="grid">
      <div v-for="(detail, index) in details" :key="index">
        <Service :title="detail.title" :url="detail.url" />
      </div>
    </div>
    <button class="submit">submit</button>
  </main>
</template>

<script>
import Header from "./components/Header.vue";
import Service from "./components/Service.vue";

export default {
  name: "App",
  components: { Header, Service },
  data() {
    return {
      details: [
        {
          title: "Family & Friends",
          url: "image-1.png",
        },
        {
          title: "Beauty & care",
          url: "image-2.png",
        },
        {
          title: "Cars Services",
          url: "image-3.png",
        },
        {
          title: "Transportation",
          url: "image-4.png",
        },
        {
          title: "House Cleaning",
          url: "image-1.png",
        },
        {
          title: "Office & Work",
          url: "image-2.png",
        },
        {
          title: "Cars Services",
          url: "image-3.png",
        },
        {
          title: "Transportation",
          url: "image-4.png",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import "./assets/sass/vars";
@import "./assets/sass/mixins";

:root {
  font-size: $font-size;
}

html,
body {
  @include reset;
}

body {
  font: {
    family: $font-family;
    size: 1.4rem;
    weight: 400;
  }
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #f8f8f8;
}

main {
  display: grid;
  grid-template-columns: auto;
  grid-auto-rows: auto;
  grid-template-areas:
    "goals"
    "grid"
    "submit";
  grid-gap: 0.5rem;
  // & > div {
  //   border: 1px solid royalblue;
  // }
}

.goals {
  grid-area: goals;
  justify-self: center;
  width: 135rem;
  height: 8rem;
  & #title {
    font-size: 3rem;
    font-weight: 500;
    margin: 2rem 0;
  }
}

.grid {
  grid-area: grid;
  justify-self: center;
  width: 135rem; // 100rem;
  height: auto; // 70rem;
  display: grid;
  grid-template-columns: auto auto auto auto;
  grid-auto-rows: auto;
  justify-content: center;
  align-content: center;
  grid-gap: 1rem;
  & div {
    animation: load 0.5s forwards;
  }
}

@keyframes load {
  from {
    opacity: 0;
    transform: translateY(-5px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.submit {
  grid-area: submit;
  justify-self: center;
  background: black;
  color: white;
  border: 1px solid black;
  border-radius: 5rem;
  text-transform: uppercase;
  padding: 1.2rem 4rem;
  margin: 3rem 0 4rem 0;
  transition: $transition-time ease-out;
  &:hover {
    cursor: pointer;
    background: white;
    color: black;
  }
}

// MEDIA
@media (max-width: 1400px) {
  .goals,
  .grid {
    width: 100rem; // 95rem;
  }

  .grid {
    grid-template-columns: auto auto auto;
  }
}

@media (max-width: 1100px) {
  .goals,
  .grid {
    width: 70rem;
  }

  .grid {
    grid-template-columns: auto auto;
  }
}

@media (max-width: 750px) {
  .goals,
  .grid {
    width: 32rem; // 26rem;
  }

  .grid {
    grid-template-columns: auto;
  }
}
</style>