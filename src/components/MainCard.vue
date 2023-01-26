<template>
  <div class="wrapper">
    <div class="main-container">
      <div class="container-one">
        <div class="profile">
          <img src="../assets/profile.png" alt="" />
          <h3>Jakcin Manoj</h3>
          <hr />
          <p>Software Developer</p>
        </div>
        <div class="social-links">
          <div class="link">
            <a href="https://github.com/JakcinManoj">
              <img src="../assets/github.png" alt="" />
              <h2>Github</h2>
            </a>
          </div>
          <div class="link">
            <a href="https://www.linkedin.com/in/jakcinmanoj">
              <img src="../assets/linkedin.png" alt="" />
              <h2>Linkedin</h2>
            </a>
          </div>
          <div class="link">
            <a href="mailto:manojjakcin@gmail.com?subject=description">
              <img src="../assets/gmail.png" alt="" />
              <h2>Gmail</h2>
            </a>
          </div>
          <div class="link">
            <a href="https://discuss.codechef.com/u/jake_jake_23">
              <img src="../assets/codechef.png" alt="" />
              <h2>CodeChef</h2>
            </a>
          </div>
        </div>
      </div>
      <div class="container-two">
        <div class="about-me">
          <h1>About Me</h1>
          <p>
            I am a fresher, <br />
            Seeking a challenging position in a reputable organization to expand
            and utilize my learning skills and knowledge. <br />
            Possess excellent communication skills and have an eye for detail.
            <br />
            Flexible to work in any environment as required.
          </p>
        </div>
        <div class="technology-section">
          <h1>Technologies Studied</h1>
          <div class="logos">
            <img src="../assets/typescript.png" alt="" />
            <img src="../assets/html&css.png" alt="" />
            <img src="../assets/nodejs.png" alt="" />
            <img src="../assets/logo.png" alt="" />
            <img src="../assets/python.png" alt="" />
            <img src="../assets/aws.png" alt="" />
            <img src="../assets/graphql.png" alt="">
          </div>
        </div>
        <div class="button-container">
          <button @click="emitToggleValue">
            <span v-if="isTrue">Hide Projects</span>
            <span v-else>Show Projects</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  emits: ["toggleValue"],
  setup(props, ctx) {
    const isTrue = ref(false);
    function emitToggleValue() {
      isTrue.value = !isTrue.value;
      console.log("----------test----------");
      ctx.emit("toggleValue", isTrue.value);
    }
    return {
      isTrue,
      emitToggleValue,
    };
  },
});
</script>

<script></script>

<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
}
img {
  height: 20px;
}

.main-container {
  display: flex;
  flex-direction: row;
  background-color: grey;
  border-radius: 25px;
  width: 80%;
  background-color: lavenderblush;
}
.profile img {
  height: 10rem;
  border-radius: 50%;
}
.link a {
  text-decoration: none;
  color: #2c3e50;
  font-size: 10px;
}

.link img {
  height: 2rem;
}

.container-one {
  background-color: peachpuff;
  padding: 2.5%;
  width: flexbox;
  border-radius: 25px;
}
.container-two {
  margin: 2.5%;
  width: flexbox;
}
.about-me {
  text-align: left;
}

.logos img {
  height: 2.5rem;
  padding: 1rem;
}


button {
  transition:  background-color 0.3s ease;
  background-color: white;
  padding: 6px 12px;
  border-radius: 25px;
  
}


@media screen and (max-width: 600px) {
  .wrapper {
    width: 95%;
  }
}
@media screen and (max-width: 516px) {
  .wrapper {
    width: 95%;
    font-size: smaller;
  }
}
@media screen and (max-width: 466px) {
  .wrapper {
    width: 95%;
    font-size: x-small;
  }
}
@media screen and (max-width: 407px) {
  .wrapper {
    width: 99%;
    font-size: xx-small;
  }
}
</style>
