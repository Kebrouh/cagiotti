<script setup>
    import { ref } from 'vue'; // Import ref from Vue


    //EMAIL STUFF HERE
    import emailjs from 'emailjs-com';

    emailjs.init("W8eOnwL6GXIH3EinA");

    const fullName = ref("");
    const email = ref("");
    const message = ref("");

    const sendEmail = async () => {
        try {
            const response = await emailjs.send("service_12hw718", "template_3i50uce", {
                from_name: fullName.value,
                email_id: email.value,
                message: message.value,
            });
            console.log("Email sent:", response);
            
            // Optionally, you can reset the form inputs
            fullName.value = "";
            email.value = "";
            message.value = "";
            alert("Envoi réussi!");
        } catch (error) {
            console.error("Email failed to send:", error);
            alert("Échec de l'envoi, veuillez-réessayer", error);
        }
    };

</script>

<template>
    
    <div class="wrap-commande">

        <div class="wrapInfo">
            <h3>Comment ca marche ?</h3>
            <p>Explorez la selection de plats ci-dessus</p>
            <p class="italic">Les plats de cette semaine sont ceux les plus a gauche</p>
            <p>Le prix est de <span>11$</span> par portion ou <span>38$</span> pour 4 portions</p>
            <p>Remplissez le formulaire avec les informations demandées</p>
            <p>Dans votre message, mentionner quels plats et la quantité désiré</p>
            <p>La date limite pour passer une commande est le samedi à <span>12h</span></p>
            <p>La date de ramassage est le lundi entre <span>14h30</span> et <span>18h30</span></p>
        </div>

        <div class="wrapForm">
            <form @submit.prevent="sendEmail">
                <input v-model="fullName" type="text" placeholder="Votre nom" required /> <br/>
                <input v-model="email" type="email" placeholder="Votre courriel" required /> <br/>
                <textarea v-model="message" placeholder="Votre commande" required></textarea> <br/>
                <button type="submit">Envoyer</button>
            </form>
        </div>

        <div class="bgi">
            <img src="@/assets/img/mider_v2.svg" alt="bgi">
        </div>

    </div>

</template>

<style scoped>

</style>