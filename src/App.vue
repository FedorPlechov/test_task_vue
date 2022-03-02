<template>
    <ThePersonalData/>
</template>

<script>
import ThePersonalData from "@/components/personalData/ThePersonalData";
export default {
  name: 'App',
  components: {
    ThePersonalData
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700&display=swap');
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Montserrat', sans-serif;
}
html {
height: 100%;
}
body {
  height: 100%;
}
#app {
  display: grid;
  grid-template-rows: 76px 1fr 76px ;
  margin: auto;
  width: 100%;
  height: 100%;
}
</style>
