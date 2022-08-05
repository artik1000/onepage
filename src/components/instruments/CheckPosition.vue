<template>
  <nav class="project-tabs">
    <div>
      <SubcategorySelect
        class="project-tabs__select"
        v-model="selectedSort"
        :options="sortOptions"
      />
    </div>
    <div class="project-tabs__items">
      <div
        class="project-tabs__item"
        v-for="tab in tabsTop"
        :key="tab.id"
        :class="{ 'project-tabs__item_selected': tab.selected === true }"
        @click="selectTab(tab, tabs = tabsTop)"
      >
        {{tab.title}}
      </div>
    </div>
  </nav>
  <div class="content-competitors" v-if="tabsTop[2].selected === true">
    <div class="content-competitors__filters"></div>
    <div class="content-competitors__charts">
      <div class="content-competitors__charts__block__title">
        <h1 class="content-competitors__charts__title">
          График позиции
          <div class="underline"></div>
        </h1>
      </div>
      <div class="tabs-category">
        <div class="tabs">
          <div
            class="tab"
            v-for="tab in tabsShow"
            :key="tab.id"
            :class="{ 'tab_active': tab.selected === true }"
            @click="selectTab(tab, tabs = tabsShow)"
          >
            <div class="tab__text">{{tab.title}}</div>
          </div>
        </div>
      </div>
      <div class="chart">
        <MyChart/>
      </div>
    </div>
  </div>
</template>

<script>
import SubcategorySelect from '@/components/SubcategorySelect'
import MyChart from "./MyChart"

export default {
  name: "CheckPosition",
  components: {
    MyChart,
    SubcategorySelect,
  },
  data () {
    return {
      selectedSort: 'Аттракционы (site.com.ua)',
      sortOptions: [
        {id: 0, name:'Аттракционы (site.com.ua)', value: 'Аттракционы (holliday-rent.com.ua)'}
      ],
      tabsTop: [
        {id: 0, title: 'Дашборд', selected: false},
        {id: 1, title: 'Динамика', selected: false},
        {id: 2, title: 'Конкуренты', selected: true},
        {id: 3, title: 'История', selected: false},
        {id: 4, title: 'Сравнение по регионам', selected: false}
      ],
      tabsShow: [
        {id: 0, title: 'Видимость конкурентов', selected: true},
        {id: 1, title: 'Средняя позиция', selected: false},
        {id: 2, title: 'Ключей в ТОП', selected: false},
      ],
    }
  },
  methods: {
    selectTab (tab, tabs) {
      let index = this.tabs.findIndex(el => el.selected === true);
      this.tabs[index].selected = false
      tab.selected = true
    },
  }
}
</script>

<style lang="scss" scoped>
.project-tabs {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 0px 24px;
  gap: 24px;
  isolation: isolate;
  width: 100%;
  max-width: 1236px;
  height: 64px;
  justify-content: space-between;


  /* Inside auto layout */

  flex: none;
  order: 0;
  align-self: stretch;
  flex-grow: 0;
  z-index: 1;
  .project-tabs__items{
    display: flex;
    flex-direction: row;
    align-self: right;
    padding: 0px;
    gap: 24px;
    height: 64px;
    width: max-content;
    .project-tabs__item {
      width: max-content;
      height: 24px;
      margin: auto;
      /* Special/16-medium */

      font-family: 'Commissioner';
      font-style: normal;
      font-weight: 500;
      font-size: 16px;
      line-height: 24px;
      /* identical to box height, or 150% */


      /* Grey/G-60 */

      color: #65676D;
    }
    .project-tabs__item_selected {
      width: max-content;
      height: 24px;
      margin: auto;
      /* Special/16-medium */

      font-family: 'Commissioner';
      font-style: normal;
      font-weight: 500;
      font-size: 16px;
      line-height: 24px;
      color: black;
    }
    .project-tabs__item:hover{
      color: black;
    }

  }
}
.project-tabs__select {
  font-family: 'Commissioner' !important;
  font-style: normal !important;
  font-weight: 600 !important;
  font-size: 16px !important;
  line-height: 24px !important;
  height: max-content;
  /* identical to box height, or 150% */


  /* Main Palette/Blue (Accent) */

  color: #3872F9 !important;
  background: white !important;

}
.content-competitors {
  overflow-x: hidden;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0px 24px;
  gap: 16px;
  isolation: isolate;

  width: 100%;
  height: 1696px;


  /* Inside auto layout */

  flex: none;
  order: 1;
  align-self: stretch;
  flex-grow: 0;
  z-index: 0;
  .content-competitors__filters {
    box-sizing: border-box;

    /* Auto layout */

    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-start;
    padding: 16px;
    gap: 12px;

    width: 100%;
    height: 68px;

    /* White */

    background: #FFFFFF;
    /* Grey/G-10 */

    border: 1px solid #E7E9F1;
    border-radius: 16px;

    /* Inside auto layout */

    flex: none;
    order: 0;
    align-self: stretch;
    flex-grow: 0;
    z-index: 2;
  }
  .content-competitors__charts {
    box-sizing: border-box;

    /* Auto layout */

    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;
    gap: 24px;

    width: 100%;
    height: 634px;

    /* White */

    background: #FFFFFF;
    /* Grey/G-10 */

    border: 1px solid #E7E9F1;
    border-radius: 16px;

    /* Inside auto layout */

    flex: none;
    order: 1;
    align-self: stretch;
    flex-grow: 0;
    z-index: 1;
  }
  .content-competitors__charts__title {
    width: 186px;
    height: 36px;

    /* Bold/B-24 */

    font-family: 'Commissioner';
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    line-height: 36px;
    margin: 0;
    /* identical to box height, or 150% */


    /* Black */

    color: #1A1A1B;


    /* Inside auto layout */

    flex: none;
    order: 1;
    flex-grow: 0;
    z-index: 2;
    position: absolute;
    .underline {
      position: absolute;
      height: 7px;
      left: 0%;
      right: 0%;
      bottom: 3px;

      /* Main Palette/Yellow */

      background: #FFD02F;

      /* Inside auto layout */

      flex: none;
      order: 0;
      flex-grow: 0;
      z-index: -1;
    }
  }
  .content-competitors__charts__block__title{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-start;
    padding: 16px 16px 0px;
    gap: 24px;

    width: 100%;
    border-radius: 16px;
    height: 52px;

    /* White */

    background: #FFFFFF;

    /* Inside auto layout */

    flex: none;
    order: 0;
    align-self: stretch;
    flex-grow: 0;
  }
  .tabs-category {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px 16px;
    gap: 24px;
    isolation: isolate;

    width: 1188px;


    /* Inside auto layout */
    .tabs {
      display: flex;
      flex-direction: row;
      align-items: flex-start;
      padding: 8px;

      width: max-content;
      height: 60px;

      /* Grey/G-5 */

      background: #F5F7FA;
      border-radius: 1000px;

      /* Inside auto layout */

      flex: none;
      order: 0;
      flex-grow: 0;
      z-index: 4;
      .tab_active{
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        padding: 10px 20px;
        gap: 6px;
        isolation: isolate;

        height: 44px;

        /* White */

        background: #FFFFFF !important;
        border-radius: 1000px;

        /* Inside auto layout */

        flex: none;
        order: 0;
        flex-grow: 0;
        color: #1A1A1B !important;
        .tab__text {
          height: 24px;

          /* Special/16-medium */

          font-family: 'Commissioner';
          font-style: normal;
          font-weight: 500;
          font-size: 16px;
          line-height: 24px;
          /* identical to box height, or 150% */


          /* Black */



          /* Inside auto layout */

          flex: none;
          order: 1;
          flex-grow: 0;
          z-index: 1;
        }
      }
      .tab{
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        padding: 10px 20px;
        gap: 6px;
        isolation: isolate;

        height: 44px;

        /* White */

        background: transparent;
        border-radius: 1000px;

        /* Inside auto layout */

        flex: none;
        order: 0;
        flex-grow: 0;
        color: #65676D;
        .tab__text {
          height: 24px;

          /* Special/16-medium */

          font-family: 'Commissioner';
          font-style: normal;
          font-weight: 500;
          font-size: 16px;
          line-height: 24px;
          /* identical to box height, or 150% */


          /* Black */



          /* Inside auto layout */

          flex: none;
          order: 1;
          flex-grow: 0;
          z-index: 1;
        }
      }
    }
  }
}
</style>
