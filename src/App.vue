<template>
  <div>
    <MainHeader />
    <HomePage />
    <MainFooter />
  </div>
</template>

<script>
import HomePage from '@/views/HomePage.vue';
import MainHeader from './components/MainHeader.vue';
import MainFooter from './components/MainFooter.vue';

export default {
  name: 'App',
  components: { HomePage, MainHeader, MainFooter }
}
</script>

<style>
@import '@/assets/css/main.css';
</style>