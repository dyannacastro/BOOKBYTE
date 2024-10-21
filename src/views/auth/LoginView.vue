<script setup>
import LoginForm from '@/components/auth/LoginForm.vue'
import { useDisplay } from 'vuetify'

const { mobile } = useDisplay()
</script>

<template>
  <v-container fluid>
    <v-row>
      <v-col cols="6" lg="6" class="bg-surface-dark h-screen text-center d-flex flex-column align-center justify-center">
        <h1 class="gradient-text">Welcome to Bookbyte</h1>
        <p class="quote-text">Discover endless knowledge and unlock your potential with every page.</p>
      </v-col>

      
      <v-col cols="12" lg="6" class="d-flex align-center justify-center" :class="mobile ? '' : 'pt-2 h-screen'">
        <v-card class="custom-card mx-auto" elevation="0">
          <v-card-title class="text-center">
            <v-img
              src="/images/book-logo.png"
              :height="mobile ? '200%' : '200'"
              contain
            ></v-img>
            <h2 class="font-weight-black">BOOKBYTE</h2>
            <h5>Login</h5>
          </v-card-title>

          <v-card-text class="pt-4">
            <v-divider class="my-5"></v-divider>

            <LoginForm></LoginForm>

            <v-divider class="my-5"></v-divider>

            <h4 class="text-center font-weight-black-">
              Don't have an account yet?
              <RouterLink to="/register" class="custom-link">
                Sign up here
              </RouterLink>
            </h4>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>

.gradient-text {
  background: linear-gradient(45deg, #64c0ce, #dd34f3);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-size: 3rem;
}

.quote-text {
  font-size: 1rem;
  margin-top: 15px; 
}

.custom-card {
  width: 100%;
  max-width: 700px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px;
}

.signup-section {
  text-align: center;
  padding-top: 1rem;
}

.signup-link {
  color: #b39ddb;
  font-weight: bold;
}

.custom-link {
  color: #b39ddb;
}
.custom-link:active, .custom-link:focus {
  color: #b39ddb;
}
</style>
