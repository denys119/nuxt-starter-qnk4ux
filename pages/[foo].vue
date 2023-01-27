<template>
  <div>
    {{ route.params.foo }}
    <nuxt-link :to="`${counter + 1}`"> Page {{ route.params.foo }} </nuxt-link>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();

const counter = computed(() => Number.parseInt(route.params.foo as string));

onMounted(() => {
  console.log('onMounted', route.params.foo);
});

onUnmounted(() => {
  console.log('onUnmounted', route.params.foo);
});
</script>
