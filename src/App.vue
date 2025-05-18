<script setup>
import { ref, computed } from 'vue';

import HelloWorld from './components/HelloWorld.vue';

const count = ref(0);

const increment = () => {
  if (count.value < 10) count.value++;
  else return;
};

const msg = computed(() => (count.value > 5 ? 'Passed' : 'Failed'));
</script>

<template>
  <HelloWorld :msg="msg" :onClick="increment" :count="count" />
</template>

<style scoped></style>

