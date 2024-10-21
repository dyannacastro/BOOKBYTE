<script setup>
import { ref, onMounted } from 'vue'

const theme = ref('light')

// Check localStorage for the theme on mount
onMounted(() => {
  const savedTheme = localStorage.getItem('theme')
  if (savedTheme) {
    theme.value = savedTheme
  }
})

// Function to toggle theme
function onToggleTheme() {
  // Toggle between light and dark modes
  theme.value = theme.value === 'light' ? 'dark' : 'light'
  localStorage.setItem('theme', theme.value)
}
</script>

<template>
  <v-responsive>
    <v-app :theme="theme">
      <v-app-bar
        class="px-3"
        :color="theme === 'light' ? 'white' : 'grey-darken-4'"
        border
      >
        <v-spacer></v-spacer>

        <v-btn
          class="me-2"
          :icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          variant="elevated"
          color="purple"
          slim
          @click="onToggleTheme"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <slot name="content"></slot>
      </v-main>

      <v-footer
        class="font-weight-bold"
        :class="mobile ? 'text-caption' : ''"
        :color="theme === 'light' ? 'white' : 'grey-darken-4'"
        border
        app
      >
        <div :class="mobile ? 'w-100 text-center' : ''">
          Copyright © 2024 - BookByte | All Rights Reserved
        </div>
      </v-footer>
    </v-app>
  </v-responsive>
</template>

