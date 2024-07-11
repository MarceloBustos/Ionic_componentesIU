<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-buttons>
                    <ion-back-button>Atrás</ion-back-button>
                </ion-buttons>
                <ion-title>Juegos</ion-title>
            </ion-toolbar>
        </ion-header>

        <ion-content class="ion-padding">
            <ion-card>
                <ion-card-header>
                    <ion-card-title>Juegos de {{ this.$route.params.consola }}</ion-card-title>
                    <ion-card-subtitle>LIstado de Video juego</ion-card-subtitle>
                </ion-card-header>

                <ion-card-content>
                    <ion-list lines="none">
                        <template v-for="(juego, i) in juegos" :key="i">
                            <ion-item v-if="juego.consola === this.$route.params.consola">
                                <ion-thumbnail>
                                    <img :src="juego.imagen" alt="imagen de juego" />
                                </ion-thumbnail>
                                <ion-label>{{ juego.nombre }}</ion-label>
                                <ion-button fill="clear" color="danger" @click="showAlert(true, i)">
                                    <ion-icon :icon="heart" slot="end"></ion-icon>
                                </ion-button>

                                <ion-button fill="clear" color="warning" @click="showToast(true, i)">
                                    <ion-icon :icon="addCircle" slot="end"></ion-icon>
                                </ion-button>
                            </ion-item>

                            <ion-alert header="Notificacion" sub-header="Exito" message="Juego añandido a favoritos"
                                :is-open="alertState[i]" @didDismiss="showAlert(false, i)" />

                            <ion-toast header="Notificacion" sub-header="Exito" message="Juego añadido a favoritos"
                                :is-open="toastState[i]" @didDismiss="showToast(false, i)" :duration="2000" />
                        </template>
                    </ion-list>
                </ion-card-content>
            </ion-card>
        </ion-content>
    </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonButtons, IonBackButton, IonTitle, IonContent, IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent, IonList, IonThumbnail, IonLabel, IonItem, IonIcon, IonAlert, IonButton, IonToast } from '@ionic/vue';

import { heart, addCircle } from 'ionicons/icons';

export default {
    name: 'Juegos',
    components: { IonPage, IonHeader, IonToolbar, IonButtons, IonBackButton, IonTitle, IonContent, IonCard, IonCardHeader, IonCardTitle, IonCardSubtitle, IonCardContent, IonList, IonThumbnail, IonLabel, IonItem, IonIcon, IonAlert, IonButton, IonToast },
    data() {
        return {
            heart, addCircle,
            alertState: [],
            toastState: [],
            juegos: [
                { consola: 'PlayStation', nombre: 'Spider-Man - Miles Morales', imagen: '/imagenes/juego1PlayStation.jpg' },
                { consola: 'PlayStation', nombre: 'God of War - Ragnarok', imagen: '/imagenes/juego2PlayStation.jpg' },
                { consola: 'PlayStation', nombre: 'The Last of Us - Parte I', imagen: '/imagenes/juego3PlayStation.jpg' },
                { consola: 'Xbox', nombre: 'Mortal Kombat X', imagen: '/imagenes/juego1Xbox.png' },
                { consola: 'Xbox', nombre: 'Hitman', imagen: '/imagenes/juego2Xbox.png' },
                { consola: 'Xbox', nombre: 'Assassins Creed Revelations', imagen: '/imagenes/juego3Xbox.png' },
                { consola: 'Nintendo Switch', nombre: 'The Legend of Zelda', imagen: '/imagenes/juego1NintendoSwitch.png' },
                { consola: 'Nintendo Switch', nombre: 'Super Mario Oddyssey', imagen: '/imagenes/juego2NintendoSwitch.png' },
                { consola: 'Nintendo Switch', nombre: 'Pokemon - Violet', imagen: '/imagenes/juego3NintendoSwitch.png' }
            ]
        }
    },
    methods: {
        showAlert(state, i) {
            this.alertState[i] = state;
        },
        showToast(state, i) {
            this.toastState[i] = state;
        }
    }
}
</script>

<style></style>