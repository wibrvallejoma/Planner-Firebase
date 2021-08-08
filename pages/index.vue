<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        <NuxtLogo />
        <VuetifyLogo />
      </v-card>
      <nuxt-link to="login">Login</nuxt-link>
      <nuxt-link to="register">Register</nuxt-link>
      <nuxt-link to="secret">Secret</nuxt-link>
    </v-col>
  </v-row>
</template>
