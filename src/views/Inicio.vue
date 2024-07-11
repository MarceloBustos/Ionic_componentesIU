<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>
                    Inicio
                </ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding">
            Inicio
        </ion-content>
    </ion-page>
</template>


<script>
import { IonPage, IonHeader, IonToolbar, IonContent, IonTitle } from "@ionic/vue";

export default {
    name: 'Tabs',
    components: {
        IonPage,
        IonHeader,
        IonToolbar,
        IonContent,
        IonTitle
    }
}
</script>

<style></style>