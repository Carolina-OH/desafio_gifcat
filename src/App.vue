<template>
  <div id="app">
    <random-gif></random-gif>
  </div>
</template>

<script>
import randomgif from './components/randomgif.vue'
  export default {
    data() {
      return {
      };
    },
        // computed: {},
    methods: {
        // -- Metodos
    },
    components: {
      'random-gif':randomgif,
    },
    
  }
</script>

