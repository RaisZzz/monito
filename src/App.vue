<template>
  <div>
    <MainHeader />
    <HomePage />
  </div>
</template>

<script>
import HomePage from '@/views/HomePage.vue';
import MainHeader from './components/MainHeader.vue';

export default {
  name: 'App',
  components: { HomePage, MainHeader }
}
</script>

<style>
@import '@/assets/css/main.css';
</style>