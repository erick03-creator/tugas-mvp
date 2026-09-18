<template>
  <ion-app>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tugas MVP</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <h1>Hello World 👋</h1>

      <p>
        Aplikasi To-Do sederhana untuk membantu mahasiswa
        mencatat tugas kuliah.
      </p>

      <ion-item>
        <ion-input
          v-model="task"
          placeholder="Masukkan tugas"
        ></ion-input>
      </ion-item>

      <ion-button expand="block" @click="addTask">
        Tambah Tugas
      </ion-button>

      <ion-list>
        <ion-item
          v-for="(item, index) in tasks"
          :key="index"
        >
          {{ item }}
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-app>
</template>

<script setup>
import { ref } from 'vue'

import {
  IonApp,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonItem,
  IonInput,
  IonButton,
  IonList
} from '@ionic/vue'

const task = ref('')
const tasks = ref([])

function addTask() {
  if (task.value.trim() !== '') {
    tasks.value.push(task.value)
    task.value = ''
  }
}
</script>