<template>
<div id="app">
  <static-train> </static-train>
  <more-option v-on:sourceChanged="sourceChanged"> </more-option>
  <information v-bind:source="source" v-bind:sourceChanged="sourceChanged"> </information>


</div>
</template>

<script>
import Trains from './trains.vue'
import Options from './Options.vue'
import Info from './Info.vue'



export default {

  components: {
    'static-train': Trains,
    'more-option': Options,
    'information': Info


  },

  data() {
    return {
      source: "",

    }
  },
  methods: {
    sourceChanged: function(source) {

      this.source = source;


    }
  }
}
</script>

<style>
#app {}
</style>
