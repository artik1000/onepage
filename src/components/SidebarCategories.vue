<template>
<div class="categories">
  <div class="categories__closebtn">
    <svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <g filter="url(#filter0_d_956_14017)">
        <rect x="12" y="6" width="24" height="24" rx="8" fill="white"/>
        <path d="M29.7738 18.7143L19.7739 18.7143L19.7739 17.2857L29.7738 17.2857L29.7738 18.7143Z" fill="#84868C"/>
        <path d="M18.2262 18L23.2262 23L23.2262 13L18.2262 18Z" fill="#84868C"/>
      </g>
      <defs>
        <filter id="filter0_d_956_14017" x="0" y="0" width="48" height="48" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
          <feFlood flood-opacity="0" result="BackgroundImageFix"/>
          <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
          <feOffset dy="6"/>
          <feGaussianBlur stdDeviation="6"/>
          <feComposite in2="hardAlpha" operator="out"/>
          <feColorMatrix type="matrix" values="0 0 0 0 0.709804 0 0 0 0 0.717647 0 0 0 0 0.752941 0 0 0 0.15 0"/>
          <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_956_14017"/>
          <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_956_14017" result="shape"/>
        </filter>
      </defs>
    </svg>
  </div>
  <div class="categories__title">
    <div class="categories__title__text">
        Инструменты
    </div>
  </div>
  <nav class="categories__submenu">
    <router-link
      class="categories__submenu__item"
      v-for="instrument in instruments"
      :to="'/instruments/' + instrument.name"
      :key="instrument.id"
    >
      {{instrument.name}}
    </router-link>
    <div class="categories__select">
      <SubcategorySelect
        v-model="selectedSort"
        :options="sortOptions"
      />
    </div>
    <router-link
      class="categories__submenu__item"
      v-for="instrumentSelect in sortOptions[sortedInstruments].options"
      :to="'/instruments/' + instrumentSelect.name"
      :key="instrumentSelect.id"
    >
      {{instrumentSelect.name}}
    </router-link>
  </nav>
</div>
</template>
<script>
import SubcategorySelect from '@/components/SubcategorySelect'
export default {
  name: 'sidebar-categories',
  components: {
    SubcategorySelect
  },
  data () {
    return {
      selectedSort: 'instrumentsBpn',
      sortOptions: [
        {
          id: 0,
          name: 'Инструменты BPN',
          value: 'instrumentsBpn',
          options: [
            {id: 0, name: 'Поиск в Webarchive'},
            {id: 1, name: 'Массовая проверка Whois'},
            {id: 2, name: 'Поиск спама в Webarchive'},
            {id: 3, name: 'Параметры ссылок'},
            {id: 4, name: 'Спам в ссылках'},
            {id: 5, name: 'Восстановление из Webarchive'},
          ]
        },
        {
          id: 1,
          name: 'No',
          value: 'No',
          options: [
            {id: 0, name: 'No'},
          ]
        },
      ],
      instruments: [
        {id: 0, name: 'Проверка Позиций'},
        {id: 1, name: 'SERP монитор'},
        {id: 2, name: 'SERM'},
        {id: 3, name: 'Wordstat'},
        {id: 4, name: 'Adwords'},
        {id: 5, name: 'Сбор подсказок'},
        {id: 6, name: 'Кластеризация'},
        {id: 7, name: 'Текстовой анализатор'},
        {id: 8, name: 'Проверка индексации'},
        {id: 9, name: 'Мета сканер'},
        {id: 10, name: 'Аудит сайта'},
      ],
    }
  },
  computed : {
    sortedInstruments () {
      console.log()
      return [...this.sortOptions].findIndex(el => el.value === this.selectedSort);
    }
  }
}
</script>

<style lang="scss" scoped>
.categories {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;
    position: absolute;
    width: 240px;
    left: 60px;
    top: 0px;
    bottom: 0px;
    background: #FAFBFD;
    .categories__closebtn{
      position: absolute;
      width: 24px;
      height: 24px;
      z-index: 2;
      right: 0;
      top: 24px;
    }

    .categories__title {
        box-sizing: border-box;

        /* Auto layout */

        display: flex;
        flex-direction: row;
        align-items: center;
        padding: 0px 16px;
        gap: 4px;

        width: 240px;
        height: 80px;

        /* Grey/G-10 */

        border-bottom: 1px solid #E7E9F1;

        /* Inside auto layout */

        flex: none;
        order: 0;
        flex-grow: 0;
        .categories__title__text {
            width: 130px;
            height: 30px;
            font-family: 'Commissioner';
            font-style: normal;
            font-weight: 600;
            font-size: 20px;
            line-height: 30px;
            color: #1A1A1B;
        }
    }
  .categories__submenu {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 24px 16px;
    gap: 12px;
    width: 240px;
    height: 664px;

  }
  a {
    text-decoration: none;
    color: inherit;
  }
  .router-link-active {
    color: #1A1A1B !important;
  }
  .router-link-active::before {
    content: "\2022";
    color: #F34C2A !important;
    font-size: 20px;
    padding-right: 15px;
  }
  .categories__submenu__item {
    width: 100%;
    height: 20px;
    font-family: 'Commissioner';
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 20px;
    color: #65676D;
  }
  .categories__submenu__item::before {
    content: "\2022";
    color: #9D9EA6;
    font-size: 20px;
    padding-right: 15px;
    flex: none;
  }
  .categories__submenu__item:hover{
     color: #1A1A1B
   }
  .categories__submenu__item:hover::before{
    color: #F34C2A !important;
  }
  .categories__select {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 8px 0px;
    gap: 4px;
    width: 208px;
    height: 52px;
  }
}
nav ul { list-style-type: none; }
</style>
