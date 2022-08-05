<template>
  <header class="top-bar">
   <div class="top-bar__title">
   <h1 class="top-bar__title__header">{{link}}</h1>
   <div class="top-bar__title__breadcrumbs">
     <div class="top-bar__title__breadcrumbs__item"><p>Главная</p></div>
     <div class="top-bar__title__breadcrumbs__item__barrier">//</div>
     <div class="top-bar__title__breadcrumbs__item"><p>{{link}}</p></div>
     <div class="top-bar__title__breadcrumbs__item__barrier">//</div>
     <div class="top-bar__title__breadcrumbs__item"><p>Результат проекта</p></div>
   </div>
   </div>
    <div class="top-bar__info">
    <div class="top-bar__balance">
      <div class="top-bar__balance__limits">
        3299
      </div>
      <div class="top-bar__balance__add">
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect width="20" height="20" rx="10" fill="#F5F7FA"/>
          <path d="M10 6.5V13.5" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M13.5 10H6.5" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
    </div>
    <div class="top-bar__alerts">
      <div>
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M4.99503 10.8333V7.5C4.99503 4.73833 7.23586 2.5 10 2.5C12.7642 2.5 15.005 4.73833 15.005 7.5V10.8333C15.005 11.655 15.3784 12.4325 16.0192 12.9475L16.2767 13.1542C17.0409 13.7675 16.6067 15 15.6267 15H4.37336C3.39336 15 2.95919 13.7675 3.72336 13.1542L3.98086 12.9475C4.62253 12.4325 4.99503 11.655 4.99503 10.8333Z" stroke="#1A1A1B" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M8.75 17.4997H11.25" stroke="#1A1A1B" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
    </div>
    <div class="top-bar__avatar">
      <img class="top-bar__avatar__icon" src="@/assets/usericon.png">
    </div>
    </div>
  </header>
</template>

<script>
export default {
    name: "TopBar",
    props: {
      link: {
        type: String
      }
    }
}
</script>

<style lang="scss" scoped>
h1 {
  margin: 0;
  padding: 0;
}
.top-bar {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 0px 24px;
  gap: 24px;
  isolation: isolate;

  position: absolute;
  height: 80px;
  left: 300px;
  right: 0px;
  top: 0px;

  /* White */

  background: #FFFFFF;
  /* Grey/G-10 */

  border-bottom: 1px solid #E7E9F1;
}
.top-bar__title {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0px;

  width: max-content;
  height: 58px;


  /* Inside auto layout */

  flex: none;
  order: 0;
  flex-grow: 0;
  z-index: 0;
}
.top-bar__title__header {
  height: 38px;

  /* Bold/B-28 */

  font-family: 'Commissioner';
  font-style: normal;
  font-weight: 600;
  font-size: 28px;
  line-height: 38px;
  /* identical to box height, or 136% */
  width: max-content;
  /* Black */

  color: #1A1A1B;


  /* Inside auto layout */

  flex: none;
  order: 0;
  flex-grow: 0;
}
.top-bar__title__breadcrumbs {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 0px;
  gap: 8px;

  width: max-content;
  height: 20px;


  /* Inside auto layout */

  flex: none;
  order: 1;
  flex-grow: 0;
  .top-bar__title__breadcrumbs__item {

    /* Regular/R-14 */

    font-family: 'Commissioner';
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    /* identical to box height, or 143% */


    /* Grey/G-60 */

    color: #65676D;


    /* Inside auto layout */
  }
  .top-bar__title__breadcrumbs__item__barrier {
    width: 8px;
    height: 16px;

    /* Regular/R-10 */

    font-family: 'Commissioner';
    font-style: normal;
    font-weight: 400;
    font-size: 10px;
    line-height: 16px;
    /* identical to box height, or 160% */


    /* Grey/G-30 */

    color: #B5B7C0;
  }
}
.top-bar__balance {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 0px;
  gap: 8px;
  isolation: isolate;
  height: 100%;
  .top-bar__balance__limits {
    font-family: 'Commissioner';
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 20px;
    color: #1A1A1B;
  }
  .top-bar__balance__limits::after {
    content: "лимитов";
    font-weight: 400;
    color: #65676D;
  }
}
.top-bar__alerts {
  padding: 32px;
  border-right: 1px solid #E7E9F1;
  border-left: 1px solid #E7E9F1;
}
.top-bar__info {
  display: flex;
  flex-direction: row;
  height: 100%;
  gap: 24px
}
.top-bar__avatar {
  padding-top: 22px;
  .top-bar__avatar__icon {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    object-fit: fill;
  }
}
</style>
