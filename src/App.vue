<script setup>
  import { RouterView } from 'vue-router'
  import HeaderApp from '@/components/commun/HeaderApp/HeaderApp.vue'
  import FooterApp from '@/components/commun/FooterApp/FooterApp.vue'
</script>

<template>
  <div class="interface">

    <HeaderApp />
    <RouterView class="contenu"/>
    <FooterApp />

  </div>
</template>

<style scoped>

</style>
