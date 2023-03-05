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
            <a :href="projectData.ProjectsArray[index].Link1" target="_blank"
              ><img src="../assets/external-link.png" alt=""
            /></a>
          </div>
          <div class="link2">
            <a :href="projectData.ProjectsArray[index].Link2" target="_blank"
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
  position: relative;
  margin: 2.5%;
  flex-wrap: 0 0 40%;
  padding: 10px;
  background: grey;
  border-radius: 25px;
  place-content: center;
  place-items: center;
  overflow: hidden;
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
}
.link2 img {
  height: 1.5rem;
  width: 1.5rem;
  border-radius: 25px;
}

@media screen and (max-width: 407px) {
  .wrapper {
    font-size: xx-small;
  }
  .project-card img {
    width: 100%;
  }
  .link1 img {
    height: 0.5rem;
    width: 0.5rem;
  }
  .link2 img {
    height: 0.5rem;
    width: 0.5rem;
  }
}
@media screen and (max-width: 656px) {
  .wrapper {
    font-size: x-small;
    align-items: center;
  }
  .project-card img {
    width: 100%;
  }
  .link1 img {
    height: 1rem;
    width: 1rem;
  }
  .link2 img {
    height: 1rem;
    width: 1rem;
  }
}
@media screen and (max-width: 439px) {
  .wrapper {
    font-size: x-small;
    align-items: center;
  }
  .project-card img {
    width: 100%;
  }
  .link1 img {
    height: 1rem;
    width: 1rem;
  }
  .link2 img {
    height: 1rem;
    width: 1rem;
    
  }
}

</style>
