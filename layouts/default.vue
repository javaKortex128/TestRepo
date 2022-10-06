<template>
  <div>
    <LazyHydrate when-visible>
    </LazyHydrate>
    <LazyHydrate when-idle>
      <AppHeader />
    </LazyHydrate>

    <div id="layout">
      <nuxt :key="$route.fullPath"/>

      <LazyHydrate when-visible>
        <BottomNavigation />
      </LazyHydrate>
      <CartSidebar />
      <WishlistSidebar />
      <LoginModal />
      <Notification />
    </div>
    <LazyHydrate when-visible>
      <AppFooter />
    </LazyHydrate>
  </div>
</template>

<script>
import AppHeader from '~/components/AppHeader.vue';
import BottomNavigation from '~/components/BottomNavigation.vue';
import AppFooter from '~/components/AppFooter.vue';
//import TopBar from '~/components/TopBar.vue';
import CartSidebar from '~/components/CartSidebar.vue';
import WishlistSidebar from '~/components/WishlistSidebar.vue';
import LoginModal from '~/components/LoginModal.vue';
import LazyHydrate from 'vue-lazy-hydration';
import Notification from '~/components/Notification';

export default {
  name: 'DefaultLayout',

  components: {
    LazyHydrate,
    //TopBar,
    AppHeader,
    BottomNavigation,
    AppFooter,
    CartSidebar,
    WishlistSidebar,
    LoginModal,
    Notification
  }
};
</script>

<style lang="scss">
@import "~@storefront-ui/vue/styles";
:root {
  --c-primary: #f8e007 !important;
  --c-avon-secondary: rgb(247, 245, 245);
  --search-bar-button-right: 10px;
  --font-family: "Montserrat", sans-serif;
  --font-family--secondary: "Montserrat", sans-serif !important;
  --font-family--tertiary: "Montserrat-Bold" !important;
  --c-background-one: #fff;
  --c-background-two: rgb(241, 241, 241);
  --c-color-one: rgb(49, 49, 49);
  --c-color-two: #000;
  --c-color-three: #fff;
  --image-width: 100% !important;
  --image-height: 664px !important;
  --text-primary: #546264;
  --text-secondary: #999;
}

#layout {
  box-sizing: border-box;
  @include for-desktop {
    max-width: 1240px;
    margin: auto;
  }
}

.no-scroll {
  overflow: hidden;
  height: 100vh;
}

// Reset CSS
html {
  width: auto;
  @include for-mobile {
    overflow-x: hidden;
  }
}
body {
  overflow-x: hidden;
  color: var(--c-text);
  font-size: var(--font-size--base);
  font-family: var(--font-family--primary);
  margin: 0;
  padding: 0;
}
a {
  text-decoration: none;
  color: var(--c-link);
  &:hover {
    color: var(--c-link-hover);
  }
}
h1 {
  font-family: var(--font-family--secondary);
  font-size: var(--h1-font-size);
  line-height: 1.6;
  margin: 0;
}
h2 {
  font-family: var(--font-family--secondary);
  font-size: var(--h2-font-size);
  line-height: 1.6;
  margin: 0;
}
h3 {
  font-family: var(--font-family--secondary);
  font-size: var(--h3-font-size);
  line-height: 1.6;
  margin: 0;
}
h4 {
  font-family: var(--font-family--secondary);
  font-size: var(--h4-font-size);
  line-height: 1.6;
  margin: 0;
}
</style>
