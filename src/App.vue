<template>
  <contador-vue :initialValue="initialValue" />
</template>

<script>
import ContadorVue from "./components/ContadorVue.vue";

export default {
  components: {
    ContadorVue,
  },
  data() {
    return {
      initialValue: 10,
    };
  },
};
</script>

<style>
</style>
