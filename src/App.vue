<template>
  <div id="app">
    <main>
    <app-header/>
      <app-grid/>
    </main>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue"
import AppGrid from "./components/AppGrid.vue"

export default {
  name: 'App',
  components: {
    AppHeader,
    AppGrid   
  }
}
</script>

<style lang="scss">
  @import './style/general';
    body {
    background-color: $background;
  }

   app-header {
     position:-webkit-sticky;
    position: sticky;
    top: 0;
  }
</style>