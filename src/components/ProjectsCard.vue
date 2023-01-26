<template>
  <div class="wrapper">
    <div class="main-container">
      <div
        class="project-card"
        v-for="(items, index) in projectData.ProjectsArray"
        v-bind:key="items"
      >
        {{ test }}

        <h2>{{ projectData.ProjectsArray[index].Title }}</h2>
        <img :src="require(`../assets/${projectData.ProjectsArray[index].Image}`)" alt="" />
        <p>{{ projectData.ProjectsArray[index].About }}</p>
        <div class="container">
          <div class="link1">
            <img src="../assets/github.png" alt="" />
            <a :href="projectData.ProjectsArray[index].Link1"
              ><img src="../assets/external-link.png" alt=""
            /></a>
          </div>
          <div class="link2">
            <a :href="projectData.ProjectsArray[index].Link2"
              ><img src="../assets/rocket.gif" alt=""
            /></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import jsonData from "/projects.json";
console.log(jsonData.ProjectsArray[0].Image);
export default {
  props: {
    test: {
      type: String,
    },
  },
  data() {
    return {
      projectData: jsonData,
    };
  },
};
</script>

<style scoped>
.main-container {
  margin-top: 5%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}
.container {
  display: flex;
  justify-content: space-between;
}
.project-card {
  margin: 10px;
  flex-wrap: 0 0 40%;
  padding: 10px;
  background-color: grey;
  border-radius: 25px;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}
.project-card img {
  height: 20rem;
  width: 40rem;
}
.link1 {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-end;
}
.link2 {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-start;
}
.link1 img {
  height: 1.5rem;
  width: 1.5rem;
  margin: 2.5px;
}
.link2 img {
  height: 1.5rem;
  width: 1.5rem;
  margin: 2.5px;
  border-radius: 25px;
}

@media screen and (max-width: 407px) {
  .wrapper {
    width: 95%;
    font-size: xx-small;
  }
  .project-card img {
    width: 300px;
  }
  .link1 img {
    height: 0.5rem;
    width: 0.5rem;
    margin: 1.5px;
  }
  .link2 img {
    height: 0.5rem;
    width: 0.5rem;
    margin: 1.5px;
  }
}
@media screen and (max-width: 656px) {
  .wrapper {
    width: 95%;
    font-size: x-small;
    align-items: center;
  }
  .project-card img {
    width: 400px;
  }
  .link1 img {
    height: 1rem;
    width: 1rem;
    margin: 1.5px;
  }
  .link2 img {
    height: 1rem;
    width: 1rem;
    margin: 1.5px;
  }
}
@media screen and (max-width: 439px) {
  .wrapper {
    width: 95%;
    font-size: x-small;
    align-items: center;
  }
  .project-card img {
    width: 340px;
  }
  .link1 img {
    height: 1rem;
    width: 1rem;
    margin: 2px;
  }
  .link2 img {
    height: 1rem;
    width: 1rem;
    margin: 2px;
  }
}
</style>
