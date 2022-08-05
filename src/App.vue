<template>
  <AreaChart/>
  <div class="side-bar">
    <div class="side-bar__logo-block">
      <svg width="24" height="14" viewBox="0 0 24 14" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M12.1 0.0866151H12.0659C11.7263 0.0625706 4.81023 -0.301303 0 7.11243C4.93894 14.313 11.9403 13.9267 12.0209 13.917C17.9011 13.8721 21.767 10.1997 24 7.06594C21.8399 3.92893 18.0066 0.131498 12.1 0.0866151ZM11.6348 12.7212V7.86743H8.70828L12.4036 1.26319V6.12019H15.4677L11.6348 12.7212Z" fill="#F34C2A"/>
      </svg>
    </div>
    <div class="side-bar__menu_block">
    <div class="side-bar__menu">
      <nav>
      <router-link class="side-bar__menu__button" to="/">
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M16.535 6.91604L11.535 3.02687C10.6325 2.32438 9.36833 2.32438 8.465 3.02687L3.465 6.91604C2.85583 7.38938 2.5 8.11771 2.5 8.88937V15.0002C2.5 16.381 3.61917 17.5002 5 17.5002H15C16.3808 17.5002 17.5 16.381 17.5 15.0002V8.88937C17.5 8.11771 17.1442 7.38938 16.535 6.91604Z" stroke="#84868C" stroke-width="1.5"/>
          <path d="M7.5 14.1667H12.5" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </router-link>
      <router-link class="side-bar__menu__button" to="/grid">
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M6.45833 8.125H4.16667C3.24583 8.125 2.5 7.37917 2.5 6.45833V4.16667C2.5 3.24583 3.24583 2.5 4.16667 2.5H6.45833C7.37917 2.5 8.125 3.24583 8.125 4.16667V6.45833C8.125 7.37917 7.37917 8.125 6.45833 8.125Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M15.8333 8.125H13.5417C12.6208 8.125 11.875 7.37917 11.875 6.45833V4.16667C11.875 3.24583 12.6208 2.5 13.5417 2.5H15.8333C16.7542 2.5 17.5 3.24583 17.5 4.16667V6.45833C17.5 7.37917 16.7542 8.125 15.8333 8.125Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M6.45833 17.5H4.16667C3.24583 17.5 2.5 16.7542 2.5 15.8333V13.5417C2.5 12.6208 3.24583 11.875 4.16667 11.875H6.45833C7.37917 11.875 8.125 12.6208 8.125 13.5417V15.8333C8.125 16.7542 7.37917 17.5 6.45833 17.5Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M15.8333 17.5H13.5417C12.6208 17.5 11.875 16.7542 11.875 15.8333V13.5417C11.875 12.6208 12.6208 11.875 13.5417 11.875H15.8333C16.7542 11.875 17.5 12.6208 17.5 13.5417V15.8333C17.5 16.7542 16.7542 17.5 15.8333 17.5Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </router-link>
        <router-link class="side-bar__menu__button" to="/instruments">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M9.8625 12.5L14.0292 16.6667C14.7192 17.3567 15.8392 17.3567 16.5292 16.6667V16.6667C17.2192 15.9767 17.2192 14.8567 16.5292 14.1667L12.3625 10" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M17.43 4.87289C17.45 4.89206 17.465 4.91706 17.4725 4.94372C17.8642 6.24956 17.5608 7.71872 16.5292 8.75039C15.4867 9.79289 13.9975 10.0912 12.6817 9.68122L5.72583 16.6371C5.04833 17.3146 3.94333 17.3654 3.2425 16.7121C2.50583 16.0262 2.49083 14.8729 3.19583 14.1671L10.1817 7.18122C9.77167 5.86539 10.07 4.37622 11.1125 3.33372C12.1442 2.30206 13.6133 1.99872 14.9192 2.39039C14.9458 2.39872 14.9708 2.41289 14.99 2.43289L15.125 2.56789C15.19 2.63289 15.19 2.73872 15.125 2.80372L12.9292 5.00039L14.8625 6.93372L17.0592 4.73706C17.1242 4.67206 17.23 4.67206 17.295 4.73706L17.43 4.87289V4.87289Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path fill-rule="evenodd" clip-rule="evenodd" d="M2.44417 3.57779L3.00583 5.26362C3.11917 5.60446 3.4375 5.83362 3.79667 5.83362H5.69583V3.93446C5.69583 3.57612 5.46667 3.25696 5.12583 3.14362L3.44 2.58196C3.29 2.53196 3.125 2.57112 3.01333 2.68279L2.545 3.15112C2.43333 3.26279 2.39417 3.42779 2.44417 3.57779V3.57779Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M5.7 5.83398L8.61667 8.75065" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </router-link>
        <router-link class="side-bar__menu__button" to="/menu">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M7.49896 5.36411H16.6694" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M16.6694 9.99985H7.49896" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M7.49896 14.6366H16.6694" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M3.7474 4.94727C3.51718 4.94727 3.33055 5.13389 3.33055 5.36411C3.33055 5.59432 3.51718 5.78095 3.7474 5.78095C3.97761 5.78095 4.16424 5.59432 4.16424 5.36411C4.16424 5.13389 3.97761 4.94727 3.7474 4.94727" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M3.7474 9.58301C3.51718 9.58301 3.33055 9.76963 3.33055 9.99985C3.33055 10.2301 3.51718 10.4167 3.7474 10.4167C3.97761 10.4167 4.16424 10.2301 4.16424 9.99985C4.16424 9.76963 3.97761 9.58301 3.7474 9.58301" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M3.7474 14.2197C3.51718 14.2197 3.33055 14.4064 3.33055 14.6366C3.33055 14.8668 3.51718 15.0534 3.7474 15.0534C3.97761 15.0534 4.16424 14.8668 4.16424 14.6366C4.16424 14.4064 3.97761 14.2197 3.7474 14.2197" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </router-link>
        <router-link class="side-bar__menu__button" to="/list">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M15 2.5H5C4.07917 2.5 3.33333 3.24583 3.33333 4.16667V15.8333C3.33333 16.7542 4.07917 17.5 5 17.5H15C15.9208 17.5 16.6667 16.7542 16.6667 15.8333V4.16667C16.6667 3.24583 15.9208 2.5 15 2.5Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M11.6667 6.25L9.58333 8.33333L8.33333 7.08333" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M6.66667 11.6667H13.3333" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M6.66667 14.1667H13.3333" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </router-link>
      </nav>
      <nav class="side-bar__menu__nav__info">
        <router-link class="side-bar__menu__button" to="/info">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M13.3347 17.5033H6.66528C4.36348 17.5033 2.49687 15.6367 2.49687 13.3349V6.66547C2.49687 4.36368 4.36348 2.49707 6.66528 2.49707H13.3347C15.6365 2.49707 17.5031 4.36368 17.5031 6.66547V13.3349C17.5031 15.6367 15.6365 17.5033 13.3347 17.5033Z" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M9.99916 6.66545C9.88412 6.66545 9.79074 6.75882 9.79158 6.87387C9.79158 6.98892 9.88495 7.08229 10 7.08229C10.115 7.08229 10.2084 6.98892 10.2084 6.87387C10.2084 6.75882 10.115 6.66545 9.99916 6.66545" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            <path d="M10.2084 13.4883V9.52832H9.37474" stroke="#84868C" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </router-link>
      </nav>
    </div>
    </div>
  </div>
  <router-view/>
</template>
<script>
export default {
  name: 'App'
}
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Commissioner:wght@100;200;300;400;500;600;700;800;900&display=swap');
html {
  line-height: 1.15; /* 1 */
  -webkit-text-size-adjust: 100%; /* 2 */
}

/* Sections
   ========================================================================== */

/**
 * Remove the margin in all browsers.
 */

body {
  margin: 0;
}

/**
 * Render the `main` element consistently in IE.
 */

main {
  display: block;
}

/**
 * Correct the font size and margin on `h1` elements within `section` and
 * `article` contexts in Chrome, Firefox, and Safari.
 */

h1 {
  font-size: 2em;
  margin: 0.67em 0;
}

/* Grouping content
   ========================================================================== */

/**
 * 1. Add the correct box sizing in Firefox.
 * 2. Show the overflow in Edge and IE.
 */

hr {
  box-sizing: content-box; /* 1 */
  height: 0; /* 1 */
  overflow: visible; /* 2 */
}

/**
 * 1. Correct the inheritance and scaling of font size in all browsers.
 * 2. Correct the odd `em` font sizing in all browsers.
 */

pre {
  font-family: monospace, monospace; /* 1 */
  font-size: 1em; /* 2 */
}

/* Text-level semantics
   ========================================================================== */

/**
 * Remove the gray background on active links in IE 10.
 */

a {
  background-color: transparent;
}

/**
 * 1. Remove the bottom border in Chrome 57-
 * 2. Add the correct text decoration in Chrome, Edge, IE, Opera, and Safari.
 */

abbr[title] {
  border-bottom: none; /* 1 */
  text-decoration: underline; /* 2 */
  text-decoration: underline dotted; /* 2 */
}

/**
 * Add the correct font weight in Chrome, Edge, and Safari.
 */

b,
strong {
  font-weight: bolder;
}

/**
 * 1. Correct the inheritance and scaling of font size in all browsers.
 * 2. Correct the odd `em` font sizing in all browsers.
 */

code,
kbd,
samp {
  font-family: monospace, monospace; /* 1 */
  font-size: 1em; /* 2 */
}

/**
 * Add the correct font size in all browsers.
 */

small {
  font-size: 80%;
}

/**
 * Prevent `sub` and `sup` elements from affecting the line height in
 * all browsers.
 */

sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}

sub {
  bottom: -0.25em;
}

sup {
  top: -0.5em;
}

/* Embedded content
   ========================================================================== */

/**
 * Remove the border on images inside links in IE 10.
 */

img {
  border-style: none;
}

/* Forms
   ========================================================================== */

/**
 * 1. Change the font styles in all browsers.
 * 2. Remove the margin in Firefox and Safari.
 */

button,
input,
optgroup,
select,
textarea {
  font-family: inherit; /* 1 */
  font-size: 100%; /* 1 */
  line-height: 1.15; /* 1 */
  margin: 0; /* 2 */
}

/**
 * Show the overflow in IE.
 * 1. Show the overflow in Edge.
 */

button,
input { /* 1 */
  overflow: visible;
}

/**
 * Remove the inheritance of text transform in Edge, Firefox, and IE.
 * 1. Remove the inheritance of text transform in Firefox.
 */

button,
select { /* 1 */
  text-transform: none;
}

/**
 * Correct the inability to style clickable types in iOS and Safari.
 */

button,
[type="button"],
[type="reset"],
[type="submit"] {
  -webkit-appearance: button;
}

/**
 * Remove the inner border and padding in Firefox.
 */

button::-moz-focus-inner,
[type="button"]::-moz-focus-inner,
[type="reset"]::-moz-focus-inner,
[type="submit"]::-moz-focus-inner {
  border-style: none;
  padding: 0;
}

/**
 * Restore the focus styles unset by the previous rule.
 */

button:-moz-focusring,
[type="button"]:-moz-focusring,
[type="reset"]:-moz-focusring,
[type="submit"]:-moz-focusring {
  outline: 1px dotted ButtonText;
}

/**
 * Correct the padding in Firefox.
 */

fieldset {
  padding: 0.35em 0.75em 0.625em;
}

/**
 * 1. Correct the text wrapping in Edge and IE.
 * 2. Correct the color inheritance from `fieldset` elements in IE.
 * 3. Remove the padding so developers are not caught out when they zero out
 *    `fieldset` elements in all browsers.
 */

legend {
  box-sizing: border-box; /* 1 */
  color: inherit; /* 2 */
  display: table; /* 1 */
  max-width: 100%; /* 1 */
  padding: 0; /* 3 */
  white-space: normal; /* 1 */
}

/**
 * Add the correct vertical alignment in Chrome, Firefox, and Opera.
 */

progress {
  vertical-align: baseline;
}

/**
 * Remove the default vertical scrollbar in IE 10+.
 */

textarea {
  overflow: auto;
}

/**
 * 1. Add the correct box sizing in IE 10.
 * 2. Remove the padding in IE 10.
 */

[type="checkbox"],
[type="radio"] {
  box-sizing: border-box; /* 1 */
  padding: 0; /* 2 */
}

/**
 * Correct the cursor style of increment and decrement buttons in Chrome.
 */

[type="number"]::-webkit-inner-spin-button,
[type="number"]::-webkit-outer-spin-button {
  height: auto;
}

/**
 * 1. Correct the odd appearance in Chrome and Safari.
 * 2. Correct the outline style in Safari.
 */

[type="search"] {
  -webkit-appearance: textfield; /* 1 */
  outline-offset: -2px; /* 2 */
}

/**
 * Remove the inner padding in Chrome and Safari on macOS.
 */

[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}

/**
 * 1. Correct the inability to style clickable types in iOS and Safari.
 * 2. Change font properties to `inherit` in Safari.
 */

::-webkit-file-upload-button {
  -webkit-appearance: button; /* 1 */
  font: inherit; /* 2 */
}

/* Interactive
   ========================================================================== */

/*
 * Add the correct display in Edge, IE 10+, and Firefox.
 */

details {
  display: block;
}

/*
 * Add the correct display in all browsers.
 */

summary {
  display: list-item;
}

/* Misc
   ========================================================================== */

/**
 * Add the correct display in IE 10+.
 */

template {
  display: none;
}

/**
 * Add the correct display in IE 10.
 */

[hidden] {
  display: none;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Commissioner', sans-serif;
}

.side-bar {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0px;

  position: absolute;
  width: 60px;
  left: 0px;
  top: 0px;
  bottom: 0px;

  /* Grey/G-5 */

  background: #F5F7FA;
  border-radius: 0px;

  .side-bar__logo-block {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 16px 12px;
    gap: 24px;

    width: 60px;
    height: 80px;

    /* Grey/G-10 */

    border-bottom: 1px solid #E7E9F1;

    /* Inside auto layout */

    flex: none;
    order: 0;
    align-self: stretch;
    flex-grow: 0;
  }
  .side-bar__menu_block{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    padding: 24px 0px;
    gap: 24px;

    width: 60px;
    height: 1784px;

    /* Inside auto layout */

    flex: none;
    order: 1;
    flex-grow: 1;
  }
  .side-bar__menu {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;

    width: 60px;
    height: 272px;

    /* Inside auto layout */

    flex: none;
    order: 0;
    flex-grow: 0;
    .side-bar__menu__nav__info {
      box-sizing: border-box;

      /* Auto layout */

      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 8px 12px;
      gap: 8px;

      width: 60px;
      height: 52px;

      /* Grey/G-10 */

      border-bottom: 1px solid #E7E9F1;

      /* Inside auto layout */

      flex: none;
      order: 1;
      flex-grow: 0;
    }
    nav {
      box-sizing: border-box;

      /* Auto layout */

      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 0px 12px 8px;
      gap: 8px;

      width: 60px;
      height: 220px;

      /* Grey/G-10 */

      border-bottom: 1px solid #E7E9F1;

      /* Inside auto layout */

      flex: none;
      order: 0;
      flex-grow: 0;
    }
    a:hover {
      background: #F34C2A;
      svg {
        path {
          stroke: #FFFFFF
        }
        fill: #F34C2A;
      }
    }
    .router-link-active {
      background: #F34C2A;
      svg {
        path {
          stroke: #FFFFFF
        }
        fill: #F34C2A;
      }
    }
    .side-bar__menu__button {
      display: flex;
      flex-direction: row;
      align-items: flex-start;
      padding: 8px;
      gap: 8px;

      width: 36px;
      height: 36px;

      border-radius: 8px;

      /* Inside auto layout */

      flex: none;
      order: 0;
      flex-grow: 0;
    }
  }
}
</style>
