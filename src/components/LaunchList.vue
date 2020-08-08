<template>
<div>
  <Loader :loading="this.$apollo.loading" />
  
    <ul class="timeline">
      <li>
          <li
          v-for="launches in allRocket"
          :key="launches.id"
          @click="$emit('select', launches);"
        >
          {{ launches.mission_name }}
        </li>
    </ul>
</div>  
</template>

<script>
import { gql } from "apollo-boost";
import Loader from "./Loader.vue";
export default {
  data() {
    return {
      allRocket: [],
      launches:[]
    };
  },
  components: { Loader },
  apollo: {
  allRocket: gql`query {
    allRocket: launches {
    launch_year
    mission_name
    links {
      flickr_images
    }
    details
    rocket {
      rocket_name
    }
    launch_success
  }
  }`
}
};
</script>

<style scoped>
.timeline {
  position: relative;
  margin-top: 20px;
  margin-left: 15%;
  padding: 1em 0;
  list-style-type: none;
  overflow: scroll;
  border-radius: 10px;
  background-color: transparent;
}
.timeline:before {
  position: absolute;
  left: 0;
  top: 0;
  content: ' ';
  display: block;
  width: 10px;
  height: 100%;
  margin-left: -3px;
  background: linear-gradient(to bottom, rgb(80,80,80, 0.8) 0%, rgb(255,255,255,0.8) 5%, rgba(255,255,255) 100%);
}
li {
  margin: 0 auto;
  padding:20px;
  list-style-type: none;
  text-align: left;
  color: white;
  cursor: pointer;
  border-bottom: 1px solid rgb(255,255,255,0.5);
}
li:hover {
  color: #6FA8DC;
}
</style>
