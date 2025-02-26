<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  data() {
    return { 
    
    }
  },
  components: {
    AppHeader,
    AppMain
  },
  methods: {
    
  }
}
</script>

<template>
  <div class="container">
    <div class="card">
      <div class="card-body">
        <AppHeader />
        <AppMain />
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@use 'assets/scss/main' as *;
// Import all of Bootstrap's CSS
@import "bootstrap/scss/bootstrap";

.container {
  padding: 50px;
}

.card {
  margin: 0 auto;
  width: 50%;
}
</style>
