<template>
  <div id="app">


    <Crontab/>
  </div>
</template>

<script>
console.log(111,Element)
</script>
<script>
import Crontab from '@/components/Crontab';

export default {
  name: 'App',
  components: {
    Crontab
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}
</style>
