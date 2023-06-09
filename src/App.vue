<script  lang="ts" setup="">
import MenuButton from './components/MenuButton.vue';
import MainNavigation from './fixtures/MainNavigation.vue';
import { ref } from 'vue';

const isMenuOpen = ref(false);
function handleMenuState(isOpen: boolean) {
  // Listen to @toggle event from MenuButton component
  // The event passes a value (isOpen), which we then
  // apply to the ref isMenuOpen so that we can pass it down
  // to MainNavigation component
  isMenuOpen.value = isOpen;
}
</script>

<template>
  <div>
    <header>
      <MenuButton @toggle="handleMenuState" />
      <MainNavigation :is-open="isMenuOpen" />
    </header>
  </div>
</template>
