<template>
  <header>
    <div class="logo"><img src="../../assets/Logo_imi_horizontal.png" alt="logo"></div>
    <nav class="nav">
      <button class="nav_link"
              @click="$emit('goTo','Form')">Форма</button>
      <button class="nav_link"
              @click="$emit('goTo','ThePreview')">Превью</button>
    </nav>
    <div class="empty"></div>
  </header>
</template>

<script>
export default {
  name: "TheHeader"
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 1px 0 rgba(17, 17, 17, 0.1);
  padding: 22px 51px;
}
.logo {
  width: 175px;
  height: 32px;
}
.nav {
  display: flex;
  justify-content: center;
  align-items: center;
}
.nav_link:first-of-type {
  padding-right: 12px;
}
.nav_link:last-of-type {
  padding-left: 12px;
}
.empty {
  max-width: 175px;
  max-height: 32px;
  width: 100%;
  height: 100%;
}
.nav_link {
  font-family: 'Montserrat', sans-serif;
  background: none;
  border: none;
  font-size: 14px;
  color: rgba(17, 17, 17, 0.48);
}
.nav_link:active,
.nav_link:hover {
  cursor: pointer;
  color: #111111;
}
</style>
