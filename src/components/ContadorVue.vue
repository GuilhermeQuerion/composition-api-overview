<template>
  <p>Initial value: {{ initialValue }}</p>
  <p>Atual value: {{count}} </p>
  <p>triple value: {{triple}} </p>
  <button @click="add"> Add</button>
</template>

<script>
import { ref, computed, watch, onMounted } from "vue";

export default {
  name: "contador-vue",
  props: {
    initialValue: Number,
  },
  setup(props) {
    const count = ref(props.initialValue);
    const triple = computed(() => count.value *3);

    watch(count, (newValue, oldValue) => {
      console.log(`new value: ${newValue} old value: ${oldValue}`)
    });

    onMounted(() =>{
      console.log('on Monted')
    });

    const add = () => {
      count.value++;
    };

    return { count, add, triple };
  },
};
</script>

<style scoped>
</style>
