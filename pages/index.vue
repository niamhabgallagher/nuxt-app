<template>
  <ion-page>
    <ion-content class="ion-padding">
      <h1>WELCOME HOME on IOS AND ANDROID</h1>
      <ion-button @click="progressToast">Click to show toast</ion-button>
    </ion-content>
  </ion-page>
</template>

<script>
import {
  heart,
  wifi,
  personCircle
} from 'ionicons/icons'

import {
  IonPage,
  IonContent,
  IonIcon,
  IonButton,
  toastController,
} from '@ionic/vue';

export default defineComponent({
  data() {
    return {
      i: {
        wifi,
        heart,
        personCircle
      },
      count: 0
    }
  },
  components: [
    IonPage,
    IonContent,
    IonIcon,
    IonButton,
  ],
  methods: {
    async progressToast() {
      const toast = await toastController.create({
        message: 'This is a toast ' + this.count + '%',
        buttons: [
          {
            text: 'Dismiss',
            role: 'cancel'
          }
        ],
      })

      toast.present();
      this.updateCountToast(toast);
    },
    updateCountToast(toast) {
      if(this.count < 100) {
        setTimeout(() => {
          this.count += 10;
          toast.message = 'this is a toast ' + this.count + '%';
          this.updateCountToast(toast);
        }, 500);
      }
    }
  },
})
</script>