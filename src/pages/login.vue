<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import { useAuthStore } from '@/stores/auth'

const auth = useAuthStore()
const username = ref('')
const password = ref('')
const router = useRouter()

const onLogin = () => {
    auth.login(username.value, password.value)

    router.push('/')
}
</script>

<template>
    <div>
       <h1>Login Page</h1>
       <div class="flex flex-col gap-2">
            {{ username }}
            <input type="text" v-model="username" class="border p-2" placeholder="Username"/>
            <input type="text" v-model="password" class="border p-2" placeholder="Password"/>
            <button @click="onLogin()" class="bg-blue-500 text-white py-1 px-3">Login</button>
        </div>
    </div>
</template>