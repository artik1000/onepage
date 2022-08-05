<template>
    <div class="instruments">
      <sidebar-categories/>
      <main class="instruments__main">
        <top-bar
          :link="this.$router.currentRoute._value.params.id"
        />
        <router-view name="instrument"/>
      </main>
    </div>
</template>

<script>
import SidebarCategories from "../components/SidebarCategories";
import TopBar from "../components/TopBar";
export default {
  name: 'OptionView',
  components: {TopBar, SidebarCategories}
}
</script>

<style lang="scss" scoped>
.instruments {
  margin-left: 60px;
  display: flex;
  flex-direction: row;
}
.instruments__main {
  display: flex;
  flex-direction: column;
}
</style>
