<template>
  <select class="select" v-model="modelValue" @change="changeOption">
    <option
      v-for="option in options"
      :key="option.id"
      :value="option.value"
    >
      {{ option.name }}
    </option>
  </select>
</template>

<script>
export default {
  name: 'my-select',
  props: {
    modelValue: {
      type: String,
    },
    options: {
      type: Object
    }
  },
  methods: {
    changeOption (event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<style lang="scss" scoped>
select{
  -moz-appearance: none;
  -webkit-appearance: none;
  border: none;
  position: relative;
  outline: none;
}
.select{
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  padding: 8px 12px;
  gap: 8px;
  isolation: isolate;

  border-radius: 8px;

  /* Inside auto layout */

  flex: none;
  order: 0;
  align-self: stretch;
  flex-grow: 0;
  background: #E7E9F1;

  font-family: 'Commissioner';
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 20px;

  color: #65676D;

}
</style>
