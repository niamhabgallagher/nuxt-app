<template>
  <ion-app>
    <ion-menu content-id="main-content" type="reveal">
      <ion-header>
        <ion-toolbar>
          <ion-title>Menu</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <ion-menu-toggle>
          <ion-item-group>
            <ion-item @click="router.push('/')">
              <ion-label>Home</ion-label>
            </ion-item>
            <ion-item @click="router.push('/about')">
              <ion-label>About</ion-label>
            </ion-item>
          </ion-item-group>
        </ion-menu-toggle>
      </ion-content>
    </ion-menu>
    <ion-page id="main-content">
      <ion-header>
        <ion-toolbar>
          <ion-buttons slot="start">
            <ion-menu-button></ion-menu-button>
          </ion-buttons>
          <ion-title>
            <IonIcon :icon="i.rocketOutline" style="color: red" size="medium"></IonIcon>
            My Nuxt App
          </ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <slot />
      </ion-content>
    </ion-page>
  </ion-app>
</template>

<script setup>
useHead({
  viewport: 'width=device-width, initial-scale=1, maximum-scale=1, viewport-fit=cover',
})
</script>

<script>
import {
  rocketOutline
} from 'ionicons/icons'

import {
  IonButtons,
  IonContent,
  IonHeader,
  IonMenu,
  IonMenuButton,
  IonPage,
  IonTitle,
  IonToolbar,
  IonIcon,
  IonApp,
  IonItemGroup,
  IonItem,
  IonLabel,
  IonMenuToggle
} from '@ionic/vue';

export default defineComponent({
  components: {
    IonButtons,
    IonHeader,
    IonMenu,
    IonMenuButton,
    IonTitle,
    IonToolbar,
    IonIcon,
    IonContent,
    IonPage,
    IonApp,
    IonItemGroup,
    IonItem,
    IonLabel,
    IonMenuToggle
  },
  data() {
    return {
      i: {
        rocketOutline,
      },
      router: useRouter(),
    }
  },
});
</script>