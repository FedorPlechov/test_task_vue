<template>
  <div class="container_column">
    <div class="container_row">
      <h3>Дети (макс. 5)</h3>
      <div>
        <button v-show="children.length<5"
                class="add_new_child"
                @click="addNewChild">
          <span></span>Добавить ребенка
        </button>
      </div>
    </div>
    <div class="container_column">
      <div v-for="child of children" :key="child.id" class="container_row">
        <BaseInput v-model="child.name"
                   label="Имя" margin-right="18px"
                   type="number"/>
        <BaseInput v-model="child.age"
                   label="Возраст"
                   margin-right="18px"
                   type="number"/>
        <button class="delete" @click="deleteInform(child.id)">Удалить</button>
      </div>
    </div>
  </div>

</template>

<script>
import BaseInput from "@/components/layouts/BaseInput";

export default {
  name: "Children",
  components: {
    BaseInput
  },
  props: ['save'],
  watch: {
    save() {
      this.$emit('saveChildren', this.children)
    }
  },
  data() {
    return {
      children: []
    }
  },
  methods: {
    addNewChild() {
      this.children.push({
        id: Date.now() * Math.random(),
        name: '',
        age: ''
      })
    },
    deleteInform(id) {
      this.children = this.children.filter(el => el.id !== id);
    }
  },
}
</script>

<style scoped>
.container_column {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: 100%;
}

h3 {
  margin: 0;
  font-size: 16px;
  color: #111111;
  padding: 20px 0;
  width: 100%;
}

h3:last-of-type {
  padding-bottom: 30px;
}

.container_row {
  display: flex;
  justify-content: flex-start;
  width: 100%;
  align-items: center;
}

.add_new_child {
  border: 2px solid #01A7FD;
  border-radius: 100px;
  padding: 10px 20px 10px 48px;
  background: none;
  font-size: 14px;
  position: relative;
  color: #01A7FD;
  min-width: 210px;
  cursor: pointer;
}

.add_new_child:active {
  transform: scale(0.9);
}

span {
  display: block;
  position: absolute;
  width: 18px;
  border-top: 3px solid #01A7FD;
  height: 1px;
  top: 18px;
  left: 20px;
}


span:after {
  content: '';
  display: block;
  position: absolute;
  width: 18px;
  border-top: 3px solid #01A7FD;
  height: 1px;
  transform: rotate(90deg);
  top: -3px;
}

.delete {
  background: none;
  border: none;
  color: #01A7FD;
  font-size: 14px;
  margin-bottom: 10px;
  cursor: pointer;
}
</style>
