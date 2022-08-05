<template>
 <div class="instrument">
   <CheckPosition
     v-if="this.$router.currentRoute._value.params.id === 'Проверка Позиций'"
   />
 </div>
</template>

<script>
import CheckPosition from "./CheckPosition";
export default {
    name: "Instrument",
  components: {CheckPosition}
}
</script>

<style lang="scss" scoped>
.instrument {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0px 0px 24px;
  isolation: isolate;

  position: absolute;
  height: 1784px;
  left: 300px;
  right: 0px;
  top: 80px;

  /* White */

  background: #FFFFFF;
}
</style>
