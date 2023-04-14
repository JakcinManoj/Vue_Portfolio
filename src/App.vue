<template>
  <MainCard @toggleValue="toggleProjects" />
  <div v-if="showProjects">
    <!-- <ProjectsCard :test="'test'" /> -->
    <ProjectsCard />
  </div>
  <footer>
    <div class="container">
      <nav>
        <ul>
          <li>
            <a href="mailto:manojjakcin@gmail.com?subject=description"
              >Contact</a
            >
          </li>
        </ul>
      </nav>

      <p>Copyright © 2023 Jakcin Manoj. All rights reserved.</p>
    </div>
  </footer>
</template>
<script>
import { ref } from "vue";
import MainCard from "./components/MainCard.vue";
import ProjectsCard from "./components/ProjectsCard.vue";

export default {
  name: "App",
  components: {
    MainCard,
    ProjectsCard,
  },

  setup() {
    let showProjects = ref(false);
    function toggleProjects(toggle) {
      console.log("ref value", toggle);
      // toggle the value of the showProjects variable
      showProjects.value = toggle;
      // call the prop function
    }

    return { toggleProjects, showProjects };
  },
};
</script>

<style>
body {
  margin: 0;
  background-image: url("./assets/background.jpg");
  background-repeat: no-repeat; /* the image will not be repeated */
  background-size: cover; /* the image will cover the entire container */
  /* background-position: center; */
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
footer {
  background-color: #333;
  padding: 2em 0;
  display: grid;
  margin-top: 5%;
  position: relative;
  bottom: 0;
  width:100%;
}

footer ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

footer li {
  display: inline-block;
}

footer a,
footer p {
  text-decoration: none;
  color: #fff;
}


</style>
