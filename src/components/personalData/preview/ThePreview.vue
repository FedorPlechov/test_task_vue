<template>
  <div class="container_data">
    <div class="container">
      <h3>Персональные данные</h3>
      <p v-show="name.trim()!=='' && age.trim()!==''">
        {{ name }}, {{ age }} лет
      </p>
      <h3 >Дети</h3>
      <p v-for="child of children"
         v-show="child.name.trim()!=='' && child.age.trim()!==''"
         :key="child.id"
         class="children">
        {{ child.name }}, {{ child.age }} лет
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ThePreview",
  props: ['form'],
  computed: {
    name() {
      return this.form.name;
    },
    age() {
      return this.form.age;
    },
    children() {
      return this.form.children;
    }
  }
}
</script>

<style scoped>
.container_data {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  min-height: 616px;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  width: 100%;
  color: #111111;
  padding-top: 20px;
  max-width: 616px;
}

h3 {
  font-size: 16px;
  font-weight: 500;
  padding: 20px 0;
}

p {
  padding-bottom: 30px;
  font-size: 16px;
  font-weight: 700;
}

.children {
  background: #F1F1F1;
  border-radius: 5px;
  padding: 10px 20px;
  margin-bottom: 20px;
}

</style>
