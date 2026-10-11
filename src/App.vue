<script setup lang="ts">
import { ref } from 'vue'

type Scene = {
  id: number;
  title: string;
  location: string;
  callTime: string;
  cast: string[];
}
const scenes = ref<Scene[]>([
  {
    id: 1,
    title: 'Opening Scene',
    location: 'Studio A',
    callTime: '08:00',
    cast: ['Actor 1', 'Actor 2', 'Actor 3']
  },
  {
    id: 2,
    title: 'Second Scene',
    location: 'Studio B',
    callTime: '09:00',
    cast: ['Actor 4', 'Actor 5']
  },
  {
    id: 3,
    title: 'Third Scene',
    location: 'Studio C',
    callTime: '10:00',
    cast: ['Actor 6', 'Actor 7']
  }
])
</script>

<template>
  <p v-if="scenes.length === 0">

    no scenes called.

  </p>
  <ul v-else>
    <li v-for="scene in scenes" :key="scene.id">
      <h3>{{ scene.title }}</h3>
      <p> Location: {{ scene.location }}</p>
      <p> Call Time: {{ scene.callTime }}</p>

    <ul>
      <li v-for="actor in scene.cast" :key="actor">
        {{ actor }}
      </li>
    </ul>
    </li>
</ul>
</template>
