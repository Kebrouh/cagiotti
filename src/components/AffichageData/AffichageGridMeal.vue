<script setup>
    import { ref } from 'vue'; // Import ref from Vue

    //DATE STUFF HERE

    const daysOfWeek = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];

    const currentDate = new Date();
    const currentDayOfWeek = ref(daysOfWeek[currentDate.getDay()]);
    const currentNumOfWeek = ref(currentDate.getDay());

    // Function to determine whether a group should move to the back
    const shouldMoveToBack = (groupNumber) => {
    if (currentDayOfWeek === 'Monday') {
        // Calculate new group order based on currentNumOfWeek
        const newGroupOrder = (groupNumber + currentNumOfWeek - 1) % 4;
        return newGroupOrder === 0;
    }
    return false;
    };
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
                    <h3>meal1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>meal2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe2" :class="{'moveToBack': shouldMoveToBack(2)}">
                <h2>groupe2</h2>
                <div class="meal1">
                    <h3>meal1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>meal2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe3" :class="{'moveToBack': shouldMoveToBack(3)}">
                <h2>groupe3</h2>
                <div class="meal1">
                    <h3>meal1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>meal2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
            <div class="groupe4" :class="{'moveToBack': shouldMoveToBack(4)}">
                <h2>groupe4</h2>
                <div class="meal1">
                    <h3>meal1</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
                <div class="meal2">
                    <h3>meal2</h3>
                    <div class="wrapImg">
                        <img src="@/assets/img/no-img.png" alt="img-placeholder">
                    </div>
                </div>
            </div>
        </div>

    </div>

</template>

<style scoped>

</style>