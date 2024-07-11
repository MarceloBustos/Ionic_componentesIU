<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>
                    Consolas
                </ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding">
            <ion-grid>
                <ion-row>
                    <ion-col v-for="(consola, i) in consolas" :key="i">
                        <ion-card>
                            <img :src="consola.imagen" height="100">
                            <ion-card-header>
                                <ion-card-title>{{ consola.nombre }}</ion-card-title>
                                <ion-card-subtitle>Juegos de {{ consola.nombre }}</ion-card-subtitle>
                            </ion-card-header>
                            <ion-card-content>{{ consola.descripcion }}</ion-card-content>
                            <ion-button :router-link="`/tabs/juego/${consola.nombre}/${consola.id}`" color="dark"
                                size="small" expand="full">
                                Explorar Juegos
                            </ion-button>
                        </ion-card>
                    </ion-col>
                </ion-row>
            </ion-grid>
        </ion-content>
    </ion-page>
</template>


<script>
import { IonPage, IonHeader, IonToolbar, IonContent, IonTitle, IonGrid, IonRow, IonCol, IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent, IonButton } from "@ionic/vue";

export default {
    name: 'Tabs',
    components: {
        IonPage,
        IonHeader,
        IonToolbar,
        IonContent,
        IonTitle,
        IonGrid,
        IonRow,
        IonCol,
        IonCard,
        IonCardHeader,
        IonCardTitle,
        IonCardSubtitle,
        IonCardContent,
        IonButton
    },
    data() {
        return {
            consolas: [
                { id: 1, nombre: 'PlayStation', descripcion: 'Juegos exclusivos para PlayStation', imagen: '/imagenes/logoPlayStation.jpg' },
                { id: 2, nombre: 'Xbox', descripcion: 'Juegos exclusivos para Xbox', imagen: '/imagenes/logoXbox.jpg' },
                { id: 3, nombre: 'Nintendo Switch', descripcion: 'Juegos exclusivos para Nintendo Switch', imagen: '/imagenes/logoNintendoSwitch.jpg' }
            ]
        }
    }
}
</script>

<style></style>