<template>
  <div class="container_inform_input" :class="{active_input: isFocus }" :style="{marginRight: marginRight}">
    <label>{{ label }}</label>
    <input
        :type="type"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
        @focus="isFocus=!isFocus"
        @blur="isFocus=!isFocus"
    />
  </div>
</template>

<script>
export default {
  name: "BaseInput",
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    },
    type: {
      type: String,
      default: 'text'
    },
    marginRight: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      isFocus: false
    }
  },
}
</script>

<style scoped>
label {
  font-style: normal;
  font-weight: normal;
  font-size: 13px;
  line-height: 16px;
  color: rgba(17, 17, 17, 0.48)
}

.container_inform_input {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
  width: 100%;
  border: 1px solid #F1F1F1;
  border-radius: 4px;
  padding: 6px 16px;
  margin-bottom: 10px;
  color: #111111;
}
.container_inform_input:hover {
  background: #C4C4C4;
  box-shadow: 0 4px 4px rgba(51, 51, 51, 0.04), 0 4px 56px rgba(51, 51, 51, 0.16);
}
.active_input {
  background: #C4C4C4;
  box-shadow: 0 4px 4px rgba(51, 51, 51, 0.04), 0 4px 56px rgba(51, 51, 51, 0.16);
}

input {
  border: none;
  width: 100%;
  font-size: 14px;
}

</style>
