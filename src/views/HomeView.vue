<script setup>
import { ref } from 'vue'
import axios from 'axios'
import { Icon } from '@iconify/vue'

const activity = ref('')
const isLoading = ref(false)
const errorMessage = ref('')

async function fetchActivity() {
  isLoading.value = true
  errorMessage.value = ''

  try {
    const response = await axios.get('https://bored-api.appbrewery.com/random')
    activity.value = response.data.activity
  } catch (error) {
    activity.value = ''
    errorMessage.value = 'No se pudo obtener una actividad. Intentalo de nuevo.'
  } finally {
    isLoading.value = false
  }
}
</script>

<template>
  <main class="view home-view">
    <section class="activity-card">
      <Icon icon="mdi:lightbulb-on-outline" class="activity-icon" aria-hidden="true" />

      <h2>Find something to do</h2>
      <p class="intro">Click the button and Unbored will suggest an activity.</p>

      <button type="button" :disabled="isLoading" @click="fetchActivity">
        {{ isLoading ? 'Loading...' : 'Get Activity' }}
      </button>

      <p v-if="activity" class="activity">{{ activity }}</p>
      <p v-if="errorMessage" class="error">{{ errorMessage }}</p>
    </section>
  </main>
</template>
