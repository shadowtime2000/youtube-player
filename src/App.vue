const { Youtube } = require("vue-youtube");

<template>
  <div id="app" class="container">
    <input v-model="video" placeholder="YouTube Link Here" class="form-control" /><br/>
    <youtube v-bind:video-id="vd" ref="youtube"/>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.min.css';
export default {
  name: 'App',
  data: function () {
    return {
      video: "",
    }
  },
  computed: {
    vd() {
      return this.$youtube.getIdFromUrl(this.video);
    }
  }
}
</script>

<style>
#app {
  text-align: center;
  background-color: red;
}
</style>
