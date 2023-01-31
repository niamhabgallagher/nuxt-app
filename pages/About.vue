<template>
  <IonPage>
    <IonContent class="ion-padding">
      <h1>WELCOME ABOUT on IOS AND ANDROID</h1>
    </IonContent>
  </IonPage>
</template>

<script>
import {
  heart,
  wifi
} from 'ionicons/icons'

import {
  IonPage,
  IonContent,
  IonIcon,
} from '@ionic/vue';

export default defineComponent({
  data() {
    return {
      i: {
        wifi,
        heart
      }
    }
  },
  components: [
    IonPage,
    IonContent,
    IonIcon
  ]
})
</script>
