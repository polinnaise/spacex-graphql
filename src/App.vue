<template>
  <div id="app">
    <h1>
      <img src="https://upload.wikimedia.org/wikipedia/commons/d/de/SpaceX-Logo.svg"
      >Launches</h1>
      <LaunchList 
        class="side" 
        @select="selectLaunch" 
      />
      <LaunchDetails
        class="main"
        v-if="selectedLaunch"
        :launches="selectedLaunch"
      />
  </div>
</template>

<script>
import LaunchList from "./components/LaunchList.vue";
import LaunchDetails from "./components/LaunchDetails.vue";

export default {
  name: "App",
  components: {
    LaunchList,
    LaunchDetails
  },

  data() {
    return {
      selectedLaunch: null
    };
  },

  methods: {
    selectLaunch(launches) {
      this.selectedLaunch = launches;
    }
  }
};
</script>

<style>
body {
  font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  color: white;
  background: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.5)) fixed, 
  url(https://images.unsplash.com/photo-1446776811953-b23d57bd21aa?w=1920&h=1080&fit=crop) 
  no-repeat center fixed;
  background-size: cover;
  min-height: 100vh;
  padding: 20px;
  font-size: 15px;
}
h1 {
  text-align: center;
  text-transform: uppercase;
}
.side {
  width: 30%;
  height: 100%;
  float: left;
}
.main {
  width: 50%;
  float: left;
}
</style>