<script lang="ts" setup>
import useAuth from "@/auth/composables/useAuth";
import AppButton from "@/auth/uiKit/AppButton.vue";
import { useRouter } from "vue-router";
const router = useRouter();
const { user } = useAuth();
</script>

<template>
  <main>
    <div class="mx-auto max-w-md mt-4 text-center">
      <h1 class="text-3xl mt-5">Vue 3 + Supabase Starter</h1>
      <div class="flex justify-around">
        <div v-if="!user">
          <AppButton @click="router.push('/auth/login')" class="mt-5">
            Log in
          </AppButton>
        </div>
        <div v-if="!user">
          <AppButton @click="router.push('/auth/register')" class="mt-5">
            Register
          </AppButton>
        </div>
        <div v-if="user">
          <p class="mt-5">
            Hi <em>{{ user.email }}</em> ! You are logged in.
          </p>
        </div>
      </div>
    </div>
  </main>
</template>
