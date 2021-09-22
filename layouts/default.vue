<template>
  <v-app dark>
    <v-main>
      <v-container>
        <v-chip>{{ $auth.loggedIn ? $auth.user.username : 'Guest' }}</v-chip>

        <div v-if="$auth.loggedIn">
          <nuxt-link :to="{ name: 'dashboard' }">
            Dashboard
          </nuxt-link>
          <v-btn @click="$auth.logout()">
            Logout
          </v-btn>
        </div>
        <div v-else>
          <nuxt-link :to="{ name: 'login' }">
            Login
          </nuxt-link>
        </div>

        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>
