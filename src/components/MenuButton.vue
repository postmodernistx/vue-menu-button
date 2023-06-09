<script  lang="ts" setup="">
import { ref } from 'vue';

const emit = defineEmits(['toggle']);
const isOpen = ref(false);

function handleClick() {
  isOpen.value = !isOpen.value; // Toggle state
  emit('toggle', isOpen.value); // Emit current state to parent component
}
</script>

<template>
  <button @click="handleClick">
    <span v-if="isOpen">Close menu</span>
    <span v-if="!isOpen">Open menu</span>
  </button>
</template>
