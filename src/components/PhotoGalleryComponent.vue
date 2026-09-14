<template>
  <ion-card>
    <ion-card-header>
      <ion-card-title>Photo Gallery</ion-card-title>
    </ion-card-header>

    <ion-card-content>
      <div v-if="photos.length === 0" class="empty-gallery">
        <p>No pictures yet.</p>
        <p>Take a picture using the camera.</p>
      </div>

      <ion-grid v-else>
        <ion-row>
          <ion-col
            v-for="(photo, index) in photos"
            :key="index"
            size="6"
          >
            <ion-img :src="photo" />
          </ion-col>
        </ion-row>
      </ion-grid>
    </ion-card-content>
  </ion-card>
</template>

<script setup lang="ts">
import {
  IonCard,
  IonCardContent,
  IonCardHeader,
  IonCardTitle,
  IonCol,
  IonGrid,
  IonImg,
  IonRow
} from '@ionic/vue';

defineProps<{
  photos: string[];
}>();
</script>

<style scoped>
.empty-gallery {
  text-align: center;
  padding: 30px;
  color: #777;
}
</style>