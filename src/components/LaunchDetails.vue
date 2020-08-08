<template>
  <div>
    <div class="window_group">
      <h3>{{ launches.mission_name }}</h3>
      <h4>Rocket</h4>
      <p>{{ launches.rocket.rocket_name }}</p>
      <h4>Mission</h4>
      <p>{{ launches.details }}</p>
      <img :src="launches.links.flickr_images" width="200" height="200" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    launches: Object
  }
};
</script>

<style scoped>
h3, h4 {
  text-align: center;
  text-transform: uppercase;
  font-weight: bold;
  color: #6FA8DC;
}
p, img {
  text-align: justify;
  width:80%;
  margin-left: 10%;
  border-radius: 15px;
}
.window_group {
  width: 500px;
  height: 600px;
  float:right;
  border-radius: 100px;
  margin-top: 10%;
  box-shadow: -1px -1px 0px 3px rgba(212, 212, 212, 1),
  3px 3px 0px 1px rgba(255, 255, 255, 1);
  background: linear-gradient(
  310deg,
rgba(2, 0, 36, 1) 0%,
rgba(9, 9, 107, 1) 0%,
rgba(0, 0, 0, 1) 80%
  );
  position: relative;
  overflow: hidden;
  box-sizing: border-box;
}
</style>
