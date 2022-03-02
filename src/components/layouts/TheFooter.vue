<template>
  <footer>
    <p>all rights reserved</p>
  </footer>
</template>

<script>
export default {
  name: "TheFooter"
}
</script>

<style scoped>
footer {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 76px;
  width: 100%;
  background: #FAFAFA;
  box-shadow: 0 1px 0 rgba(17, 17, 17, 0.1);
}
p {
  font-size: 13px;
  color: #000000;
}
</style>
