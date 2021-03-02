<template>
  <div id="app">
    <div class="container">
      <h1 class="item">Hello Frontend Devs</h1>
      <h3 class="item">What is your favorite JS framework?</h3>
      <div class="item">
        <button @click="updateChoice" value="Angular">Angular</button>
        <button @click="updateChoice" value="Vue">Vue</button>
        <button @click="updateChoice" value="React">React</button>
      </div>
      <p v-if="choice" class="item">
        Good choice! {{ choice }} is a great tool!
      </p>
      <div class="item">
        <img :src="image" :alt="choice" height="350px" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      choice: "",
      image: "",
    };
  },
  methods: {
    updateChoice(e) {
      this.choice = e.target.value;

      switch (e.target.value) {
        case "Angular":
          this.image =
            "https://angular.io/assets/images/logos/angular/angular.png";
          break;
        case "Vue":
          this.image =
            "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1184px-Vue.js_Logo_2.svg.png";
          break;
        case "React":
          this.image =
            "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1280px-React-icon.svg.png";
          break;
        default:
      }
    },
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
}

.item {
  display: flex;
  justify-content: center;
}
</style>
