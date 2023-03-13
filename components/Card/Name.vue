<script setup lang="ts">
  interface NameProps {
    name: string;
    index: number;
  }

  const props = defineProps<NameProps>();
  const emit = defineEmits(['remove']);
  
  const removeName = () => {
    emit('remove', props.index);
  };
</script>

<template>
  <div class="card">
    <h4>{{ name }}</h4>
    <span @click="removeName">X</span>
  </div>
</template>

<style scoped>
  .card {
    position: relative;
    background-color: rgb(27, 60, 138);
    flex: 0 1 calc(100% / 3 - .8999rem);
    color: white;
    border-radius: 1rem;
    padding: 0.1rem;
    position: relative;
  }
  .card span {
    position: absolute;
    display: block;
    top: 10%;
    left: 92.5%;
    cursor: pointer;
    color: rgb(249, 87, 89);
  }
</style>
