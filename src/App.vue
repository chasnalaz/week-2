<script setup lang="ts">
import { useAuthStore } from '@/stores/auth'
import { useRouter } from 'vue-router'

const auth = useAuthStore()
const router = useRouter()

const onLogout = () => {
  auth.logout()
  router.push('/login')
}
</script>

<template>
  <div class="flex flex-col container mx-auto p-4 gap-10">

    <div class="flex justify-between">

      <div class="flex gap-4">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/restricted">Restricted Page</router-link>
      </div>

      <div class="flex gap-2 items-center">
        <p v-if ="auth.username">{{ auth.username }}</p>
        <div v-if="auth.username">
          <button class="bg-red-500 text-white py-1 px-3" @click="onLogout()">Logout</button>
        </div>
        <div v-else>
          <router-link class="bg-blue-500 text-white py-1 px-3" to="/login">Login</router-link>
          <router-link v-if="auth.username" to="/restricted">restricted Page</router-link>
        </div>
      </div>
    </div>
    <router-view></router-view>
  </div>

</template>