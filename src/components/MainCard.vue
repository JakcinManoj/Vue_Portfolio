<template>
  <div class="wrapper">
    <div class="main-container">
      <div class="container-one">
        <div class="profile">
          <img src="../assets/profile.png" alt="" />
          <h2>Jakcin Manoj</h2>
          <hr />
          <h2>Software Developer</h2>
        </div>
        <div class="social-links">
          <div class="link">
            <a href="https://github.com/JakcinManoj" target="_blank">
              <img src="../assets/github.png" alt="" />
              <h2>Github</h2>
            </a>
          </div>
          <div class="link">
            <a href="https://www.linkedin.com/in/jakcinmanoj" target="_blank">
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
            <a
              href="https://discuss.codechef.com/u/jake_jake_23"
              target="_blank"
            >
              <img src="../assets/codechef.png" alt="" />
              <h2>CodeChef</h2>
            </a>
          </div>
          <label class="label">
            <div class="toggle" :class="{ blue: isTrue }">
              <input
                @click="emitToggleValue"
                class="toggle-state"
                type="checkbox"
                name="check"
                value="check"
              />
              <div class="indicator"></div>
            </div>
          </label>
          <p></p>
          <span
            style="
              font-weight: bold;
              font-family: Arial, Helvetica, sans-serif;
              font-size: 15px;
            "
            >Show Projects</span
          >
          <p></p>
        </div>
      </div>
      <div class="container-two">
        <div class="about-me">
          <h1>About Me</h1>
          <p>
            I am a Problem Solver,<br />
            Passionate problem solver eager to contribute to real-world
            challenges.
            Committed to continuous learning and growth.
            Seeking opportunities to innovate and make meaningful contributions.
          </p>
        </div>
        <div class="Tools">
          <h1>Tools</h1>
          <div class="logos">
            <img src="../assets/github.png" alt="" />
            <img src="../assets/vscode.png" alt="" />
            <img src="../assets/dbeaver.png" alt="" />
            <img src="../assets/postman.png" alt="" />
            <img src="../assets/docker.png" alt="" />
            <img src="../assets/bitbucket.png" alt="" />
          </div>
        </div>
        <div class="technology-section">
          <h1>Technical Skills</h1>
          <div class="logos">
            <img src="../assets/typescript.png" alt="" />
            <img src="../assets/html&css.png" alt="" />
            <img src="../assets/nodejs.png" alt="" />
            <img src="../assets/logo.png" alt="" />
            <img src="../assets/python.png" alt="" />
            <img src="../assets/aws.png" alt="" />
            <img src="../assets/graphql.png" alt="" />
            <img src="../assets/postgres.png" alt="" />
            <img src="../assets/mongodb.png" alt="" />
            <img src="../assets/nestjs.png" alt="" />
            <img src="../assets/java.gif" alt="" />
          </div>
          <div class="resume">
            <h3>CV</h3>
            <a
              href="https://drive.google.com/file/d/1BjMWgd1YKs2_VfyLN9LVxoVKkl_5tgqC/view?usp=sharing"
              target="_blank"
              ><img src="../assets/cv.png" alt=""
            /></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  emits: ['toggleValue'],
  setup(props, ctx) {
    const isTrue = ref(false);
    function emitToggleValue() {
      isTrue.value = !isTrue.value;
      console.log('----------test----------');
      ctx.emit('toggleValue', isTrue.value);
    }
    return {
      isTrue,
      emitToggleValue,
    };
  },
});
</script>

<style scoped>
.toggle.blue .indicator {
  background-color: orange;
}

.resume {
  display: grid;

  margin-top: 1rem;
  height: 2rem;
  padding: 1rem;
}

.resume img {
  height: 2rem;
}

.label {
  display: inline-flex;
  align-items: center;
  cursor: pointer;
  color: #394a56;
}

.toggle {
  isolation: isolate;
  position: relative;
  height: 25px;
  width: 50px;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: -8px -4px 8px 0px #ffffff, 8px 4px 12px 0px #d1d9e6,
    4px 4px 4px 0px #d1d9e6 inset, -4px -4px 4px 0px #ffffff inset;
}

.toggle-state {
  display: none;
}

.indicator {
  height: 100%;
  width: 200%;
  background: #ecf0f3;
  border-radius: 15px;
  transform: translate3d(-75%, 0, 0);
  transition: transform 0.4s cubic-bezier(0.85, 0.05, 0.18, 1.35);
  box-shadow: -8px -4px 8px 0px #ffffff, 8px 4px 12px 0px #d1d9e6;
}

.toggle-state:checked ~ .indicator {
  transform: translate3d(25%, 0, 0);
}

.technology-section {
  text-align: center;
}
.wrapper {
  display: flex;
  justify-content: center;
}
img {
  height: 20px;
}

.main-container {
  display: flex;
  flex-direction: both;
  border-radius: 25px;
  background-color: rgba(241, 237, 237, 0.194);
  margin: 1%;
  text-align: center;
  overflow: auto;
  margin-bottom: 10%;
  box-shadow: -20px -20px 60px #5b5252, 20px 20px 60px #7b7070;
}

.profile {
  text-decoration: none;
  color: #2c3e50;
  font-size: 10px;
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
  background-color: whitesmoke;
  width: flexbox;
  border-radius: 25px;
  margin-right: 2.5%;
}
.container-two {
  padding: 2.5%;
  background-color: lavenderblush;
  width: flexbox;

  overflow: auto;
  border-radius: 25px;
}
.about-me {
  text-align: left;
}

.logos img {
  height: 2.5rem;
  padding: 1rem;
}

@media screen and (max-width: 516px) {
  .wrapper {
    font-size: smaller;
  }
}
@media screen and (max-width: 466px) {
  .wrapper {
    font-size: x-small;
  }
}
@media screen and (max-width: 407px) {
  .wrapper {
    font-size: xx-small;
  }
}
</style>
