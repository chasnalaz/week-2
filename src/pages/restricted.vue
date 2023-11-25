<script setup lang="ts">
import { useAuthStore } from '@/stores/auth';

const auth = useAuthStore();
</script>

<template>
    <div>
        <div v-if="auth.username">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Minus maxime voluptatem repellendus reiciendis error voluptas saepe quam eos amet. Saepe a deleniti id asperiores voluptatibus magni adipisci dolorum laboriosam corrupti?
        </div>
        <div v-else>Silakan Login terlebih dahulu</div>
    </div>
</template>
