<template>
  <v-container>
    <v-row align="center" justify="center">
      <v-col cols="12" lg="5" md="6" sm="8">
        <v-card>
          <v-card-text>
            <v-form>
              <v-text-field v-model="fields.username" label="Username" />
              <v-text-field v-model="fields.password" label="Password" type="password" />
              <v-checkbox v-model="fields.remember" label="Remember me" />
            </v-form>
          </v-card-text>
          <v-divider />
          <v-card-actions>
            <v-btn color="primary" @click="login">
              Login
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Login',
  auth: 'guest',

  data () {
    return {
      fields: {
        username: null,
        password: null,
        remember: false
      }
    }
  },

  methods: {
    login () {
      this.$auth.loginWith('laravelSanctum', {
        data: {
          username: this.fields.username,
          password: this.fields.password
        }
      })
    }
  }
}
</script>
