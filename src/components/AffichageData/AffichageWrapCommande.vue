<script setup>
    import { ref } from 'vue'; // Import ref from Vue

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
            <p>Explorez la selection de plat ci-dessus</p>
            <p>Assurez-vous de quels vendredi vous pouvez le commander pour</p>
            <p>Remplissez le formulaire avec les informations demandées</p>
            <p>Dans votre message, mentionner quels plats et la quantité désiré</p>
        </div>

        <div class="wrapForm">
            <form @submit.prevent="sendEmail">
                <input v-model="fullName" type="text" placeholder="Votre nom" required /> <br/>
                <input v-model="email" type="email" placeholder="Votre courriel" required /> <br/>
                <textarea v-model="message" placeholder="Votre commande" required></textarea> <br/>
                <button type="submit">Envoyer</button>
            </form>
        </div>

    </div>

</template>

<style scoped>

</style>