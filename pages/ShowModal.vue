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
        <!-- <ion-fab-button>
          <ion-icon name="document"></ion-icon>
        </ion-fab-button>
        <ion-fab-button>
          <ion-icon name="color-palette"></ion-icon>
        </ion-fab-button>
        <ion-fab-button>
          <ion-icon name="globe"></ion-icon>
        </ion-fab-button> -->
        <ion-item>
          <ion-label>Loading 1</ion-label>
        </ion-item>
        <ion-item>
          <ion-label>Loading 2</ion-label>
        </ion-item>
        <ion-item>
          <ion-label>Loading 3</ion-label>
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
  IonLabel
} from '@ionic/vue';
import { defineComponent, ref } from 'vue';
import { listCircleOutline } from 'ionicons/icons';
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
    IonLabel
  },
  setup() {
    const isOpenRef = ref(false);
    const setOpen = (state: boolean) => (isOpenRef.value = state);

    return { isOpenRef, setOpen };
  },
  data() {
    return {
      listCircleOutline
    }
  }
});
</script>