<template>
  <ion-content>
    <ion-button @click="setOpen(true)">Show Loading</ion-button>
    <ion-loading :is-open="isOpenRef" cssClass="my-custom-class" message="Please wait..." :duration="timeout"
      @didDismiss="setOpen(false)" mode="ios" translucent="true" show-backdrop="false">
    </ion-loading>

    <ion-fab slot="fixed" vertical="bottom" horizontal="start">
      <ion-fab-button>
        <ion-icon :icon="listCircleOutline"></ion-icon>
      </ion-fab-button>
      <ion-fab-list side="top">
        <ion-item v-for="item in items" :key="item.num" style="width: 250px" lines="none">
          <ion-card class="loading-card">
            <ion-card-header>
              <ion-card-title>
                {{ item.title }}
                <ion-icon @click="clickMe(item.num)" :icon="close" style="margin-left: 45px;"></ion-icon>
              </ion-card-title>
            </ion-card-header>
            <ion-card-content>
              <ion-progress-bar :color="item.color" type="indeterminate"></ion-progress-bar>
            </ion-card-content>
          </ion-card>
        </ion-item>
      </ion-fab-list>
    </ion-fab>
  </ion-content>
</template>

<script lang="ts">
import { 
  IonButton, 
  IonContent, 
  IonLoading,
  IonFab,
  IonFabButton,
  IonFabList,
  IonItem,
  IonLabel,
  IonCard,
  IonCardContent,
  IonProgressBar,
  IonIcon,
  IonCardHeader,
  IonCardTitle,
} from '@ionic/vue';
import { defineComponent, ref } from 'vue';
import { listCircleOutline, close } from 'ionicons/icons';
export default defineComponent({
  props: {
    timeout: { type: Number, default: 1000 },
  },
  components: { 
    IonButton, 
    IonContent, 
    IonLoading,
    IonFab,
    IonFabButton,
    IonFabList,
    IonItem,
    IonLabel,
    IonCard,
    IonCardContent,
    IonProgressBar,
    IonIcon,
    IonCardHeader,
    IonCardTitle,
  },
  setup() {
    const isOpenRef = ref(false);
    const setOpen = (state: boolean) => (isOpenRef.value = state);

    return { isOpenRef, setOpen };
  },
  data() {
    return {
      listCircleOutline,
      close,
      items: [
        { title: 'Loading 1', num: 1, color: 'primary' },
        { title: 'Loading 2', num: 2, color: 'secondary' },
        { title: 'Loading 3', num: 3, color: 'tertiary' },
        { title: 'Loading 4', num: 4, color: 'success' },
      ]
    }
  },
  methods: {
    clickMe(event: number) {
      console.log('close', event);
    }
  },
});
</script>

<style scoped>
.loading-card {
  width: 100% !important;
}
</style>