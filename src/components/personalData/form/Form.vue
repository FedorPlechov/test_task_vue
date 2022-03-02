<template>
  <form class="form" @submit.prevent>
    <div class="container">
      <NameAndAge :save="save" @saveNameAndAge="$emit('saveNameAndAge', $event)"/>
      <Children :save="save" @saveChildren="$emit('saveChildren', $event)"/>
      <div class="container_button">
        <button class="button_save" @click="saveInformation">Сохранить</button>
      </div>
    </div>
  </form>
</template>

<script>
import NameAndAge from "@/components/personalData/form/NameAndAge";
import Children from "@/components/personalData/form/Children";

export default {
  name: "Form",
  components: {
    NameAndAge,
    Children
  },
  data() {
    return {
      save: false
    }
  },
  methods: {
    saveInformation() {
      this.save = !this.save;
    }
  }
}
</script>

<style scoped>
.form {
  display: flex;
  justify-content: center;
  align-items: flex-start;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  max-width: 616px;
  width: 100%;
}

.button_save {
  border: 2px solid #01A7FD;
  border-radius: 100px;
  padding: 10px 20px;
  background: #01A7FD;
  font-size: 14px;
  color: white;
  min-width: 118px;
  cursor: pointer;
}

.button_save:hover,
.button_save:active {
  background: white;
  color: #01A7FD;
}

.button_save:active {
  transform: scale(0.9);
}

.container_button {
  display: flex;
  width: 100%;
  padding-top: 20px;
}
</style>
