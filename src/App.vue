<template>
  <HelloWorld/>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';
import HelloWorld from './components/HelloWorld.vue';

export default defineComponent({
  name: 'App',
  components: {
    HelloWorld,
  },
});
</script>

<style lang="scss">

</style>
