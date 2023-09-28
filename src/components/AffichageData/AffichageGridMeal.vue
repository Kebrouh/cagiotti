<script setup>
    import { computed } from 'vue';
    import { DateTime } from "luxon";

    //DATE STUFF HERE
    
    // Store the launch date as a DateTime instance
    const launchDate = DateTime.fromISO('2023-08-21')
    
    // Get the current date and time as a DateTime instance
    const currentDate = DateTime.local();
    
    // Calculate the difference between current date and launch date
    const duration = currentDate.diff(launchDate);
    
    // Convert the duration to weeks and round down
    const totalWeeks = Math.floor(duration.as('weeks'));
    
    console.log(totalWeeks)

    // Computed property to determine the class based on the alternating number
    const getClassNumber = computed(() => {
        const classNumber = totalWeeks % 4;
        return `grid-${classNumber}`;
    });
    
</script>

<!-- USE MODULO -->
<!-- permet de faire des boucle de passer a travers un tableau sans nécessairement recommencer -->
<!-- truc a installer sur les autres postes : npm install --save luxon -->
<!-- faire que la class de grid glob décide de l'order des groupes
        ex: grid-0 = 1 2 3 4
            grid-1 = 2 3 4 1 etc.. 

            a changer dans pemana 430 3330-->

<template>

    <div class="grid-meal">
        <div class="wrapInfo">
            <p>Plats pour ce lundi !</p>
            <div class="wrapImg">
                <img src="@/assets/img/arrow.svg" alt="arrow">
            </div>
        </div>
        
        <div class="grid" :class="getClassNumber">
            <div class="groupe1">
                <!-- <h2>groupe1</h2> -->
                <div class="meal1">
                    <h3>Croquette de morue, patates avec salade de chou & sauce tartare</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/croquette_morue.jpg" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>Bœuf Stroganoff et pommes de terre pilées</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/stroganoff.jpg" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe2">
                <!-- <h2>groupe2</h2> -->
                <div class="meal1">
                    <h3>Rigatoni à la bolognaise</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/rigatoni.jpg" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>Bœuf braisé au Barolo et légumes poêlés</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/boeuf_braise.jpg" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe3">
                <!-- <h2>groupe3</h2> -->
                <div class="meal1">
                    <h3>Risotto aux tomates séchées, roquette et chèvre</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/risotto.jpg" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>Tortellini à la sauce rosée</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/tortelini.jpg" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe4">
                <!-- <h2>groupe4</h2> -->
                <div class="meal1">
                    <h3>Salade de pâtes à la grecque</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/salade_grec.jpg" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>Chili con carne</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/chili.jpg" alt="img-placeholder">
                    </div>
                </div>
            </div>
        </div>

    </div>

</template>

<style scoped>

</style>