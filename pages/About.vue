<template>
  <IonPage>
    <IonHeader :translucent="true">
      <IonToolbar mode="md">
        <IonTitle>About</IonTitle>
      </IonToolbar>
    </IonHeader>
    <IonContent class="ion-padding">
      <h1>WELCOME ABOUT on IOS AND ANDROID</h1>
      <IonButton @click="router.push('/')">
        Go to Home Page
      </IonButton>
    </IonContent>
  </IonPage>
</template>

<script setup>
import {
  IonHeader,
  IonPage,
  IonToolbar,
  IonTitle,
  IonContent,
  IonButton
} from '@ionic/vue';

const router = useRouter();
</script>

scrip
