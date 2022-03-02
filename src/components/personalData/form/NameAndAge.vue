<template>
  <div class="container_inform">
    <h3>Персональные данные</h3>
    <BaseInput v-model="name" label="Имя"/>
    <BaseInput v-model="age" label="Возраст" type="number"/>
  </div>
</template>

<script>
import BaseInput from "@/components/layouts/BaseInput";

export default {
  name: "NameAndAge",
  components: {
    BaseInput
  },
  props: ['save'],

  watch: {
    save() {
      this.$emit('saveNameAndAge', {name: this.name, age: this.age});
    }
  },
  data() {
    return {
      name: '',
      age: ''
    }
  }
}
</script>

<style scoped>
.container_inform {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: 100%;
}

input {
  border: none;
  width: 100%;
  font-size: 14px;
}

h3 {
  margin: 0;
  font-size: 16px;
  color: #111111;
  padding: 20px 0;
}

label {
  font-style: normal;
  font-weight: normal;
  font-size: 13px;
  line-height: 16px;
  color: rgba(17, 17, 17, 0.48)
}
</style>
