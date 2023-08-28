<script setup>
    import { ref } from 'vue'; // Import ref from Vue

    //DATE STUFF HERE

    const daysOfWeek = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];

    const currentDate = new Date();
    const currentDayOfWeek = ref(daysOfWeek[currentDate.getDay()]);
    const currentNumOfWeek = ref(currentDate.getDay());

    console.log("hello  yes i am awake");

    const shouldMoveToBack = () => {
        console.log("skadoosh");
        return currentDayOfWeek.value === 'Monday';
    };

    // Function to determine whether a group should move to the back
    // const shouldMoveToBack = (groupNumber) => {
    //     if (currentDayOfWeek.value === 'Monday') { // Fix this line
    //         const currentWeekDayNumber = currentNumOfWeek.value;
    //         const newGroupOrder = (groupNumber + currentWeekDayNumber - 1) % 4;
    //         console.log(groupNumber + " + " + currentNumOfWeek.value + " = " + newGroupOrder);
    //         return newGroupOrder === 0;
    //     }
    //     console.log("cringe lmao");
    //     return false;
    // };
</script>

<template>

    <div class="grid-meal">
        <div class="wrapInfo">
            <p>Choix de repas selon le vendredi du mois à venir</p>
        </div>

        <!-- temp -->
        <div>
            Today is {{ currentDayOfWeek }}
            Today is {{ currentNumOfWeek }}
        </div>
        
        <div class="grid">
            <div class="groupe1" :class="{'moveToBack': shouldMoveToBack(1)}">
                <h2>groupe1</h2>
                <div class="meal1">
                    <h3>G1-M1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>G1-M2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe2" :class="{'moveToBack': shouldMoveToBack(2)}">
                <h2>groupe2</h2>
                <div class="meal1">
                    <h3>G2-M1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>G2-M2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe3" :class="{'moveToBack': shouldMoveToBack(3)}">
                <h2>groupe3</h2>
                <div class="meal1">
                    <h3>G3-M1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>G3-M2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe4" :class="{'moveToBack': shouldMoveToBack(4)}">
                <h2>groupe4</h2>
                <div class="meal1">
                    <h3>G4-M1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>G4-M2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
        </div>

    </div>

</template>

<style scoped>
    .grid {
        display: flex;
    }

    .groupe1, .groupe2, .groupe3, .groupe4 {
        flex: 1;
        transition: order 1s ease-in-out; /* Adjust the duration and timing function as needed */
    }

    .moveToBack {
        order: -1;
    }
</style>