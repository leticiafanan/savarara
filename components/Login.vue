<script setup lang="ts">
import { loginData } from '~/mock/loginData';
</script>

<template>
  <div>
    <div class="div-logo">
      <img :src="loginData.logo.src" alt="Logo">
      <h1 class="title">{{ loginData.logo.title }}</h1>
    </div>
    
    <div class="form-container">
      <h2>{{ loginData.registrationForm.title }}</h2>
      <form>
        <div v-for="field in loginData.registrationForm.fields" :key="field.id">
          <label :for="field.id">{{ field.label }}</label>
          <input :type="field.type" :id="field.id" :required="field.required" />
        </div>
        <div class="error"></div>
        <button class="button-register" type="submit">
          {{ loginData.registrationForm.button }}
        </button>
      </form>
    </div>

    <!-- Login Form -->
    <div class="form-container-login">
      <h2>{{ loginData.loginForm.title }}</h2>
      <form>
        <div v-for="field in loginData.loginForm.fields" :key="field.id">
          <label :for="field.id">{{ field.label }}</label>
          <input
            :type="field.type"
            :id="field.id"
            :required="field.required"
            class="input-login"
          />
        </div>
        <button class="button-login" type="submit">
          {{ loginData.loginForm.button }}
        </button>
      </form>
    </div>
  </div>
</template>
