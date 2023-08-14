<script setup>
    import AffichageGridMeal from '@/components/AffichageData/AffichageGridMeal.vue'
    import AffichageWrapCommande from '@/components/AffichageData/AffichageWrapCommande.vue'
    import AffichageWrapMap from '@/components/AffichageData/AffichageWrapMap.vue'
    

    import { onBeforeMount } from 'vue'
    onBeforeMount(() => {
        window.scrollTo({top:0});
    })
</script>

<template>
    
    <div class="accueil">

        component grid bouffe
        <AffichageGridMeal/>

        component wrap info
        <AffichageWrapCommande/>

        component wrap map
        <AffichageWrapMap/>

    </div>

</template>

<style scoped>

</style>
