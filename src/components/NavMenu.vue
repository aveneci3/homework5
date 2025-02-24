<template>
  <nav class="bg-slate-900 h-20 flex items-center justify-center text-white">
    <div class="flex space-x-4">
      <RouterLink :to="{name: 'Home'}">Home</RouterLink>
      <RouterLink :to="{name: 'Other'}">Other</RouterLink>
      <RouterLink :to="{name: 'SettingsPage'}">Settings</RouterLink>

      <div v-if="isAuthenticated">
        Welcome {{ user.email }}
        <button @click="logout" class="rounded-md bg-red-500 px-4 py-2 mx-2 text-red-100 hover:bg-red-700">LOGOUT</button>
      </div>
      <div v-else>
        <RouterLink :to="{name: 'LoginPage'}">Login</RouterLink>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { useAuth } from '../composables/useAuth'
const { isAuthenticated, logout, user} = useAuth()
</script>