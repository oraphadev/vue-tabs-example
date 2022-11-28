<template>
  <div id="app">
    <Tabs />
  </div>
</template>

<script>
import Tabs from '@/components/Tabs'

export default {
  name: 'App',
  components: {
    Tabs
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: 'Outfit';
}

body, html {
  margin: 0;
  padding: 0;
  background: #17181a;
}

span {
  font-family: 'Material Symbols Outlined';
  font-weight: normal;
  font-style: normal;
  font-size: 24px;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  font-feature-settings: 'liga';
  -webkit-font-feature-settings: 'liga';
  -webkit-font-smoothing: antialiased;
}
</style>

<style scoped>
#app {
  align-items: center;
  display: flex;
  justify-content: center;
  width: 100%;
  min-height: 100vh;
}
</style>
