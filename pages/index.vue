<template>
  <IonPage>
    <IonHeader :translucent="true">
      <IonToolbar mode="md">
        <IonTitle>Home</IonTitle>
        <IonIcon :icon="i.heart" style="color: red" size="large"></IonIcon>
        <!-- <IosHeartIcon w="60px" h="60px" animate="beat" /> -->
      </IonToolbar>
    </IonHeader>
    <IonContent class="ion-padding">
      <h1>WELCOME HOME on IOS AND ANDROID</h1>
      <IonButton @click="router.push('/about')">
        Go to About Page
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
  IonButton,
  IonIcon
} from '@ionic/vue';

const router = useRouter();
</script>

<script>
import {
  heart,
  wifi
} from 'ionicons/icons'

export default {
  data() {
    return {
      i: {
        wifi,
        heart
      }
    }
  }
}
</script>
