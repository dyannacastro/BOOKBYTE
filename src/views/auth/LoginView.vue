<script setup>
import LoginForm from '@/components/auth/LoginForm.vue'
import { useDisplay } from 'vuetify'

const { xs, smAndDown } = useDisplay();  
</script>

<template>
  <v-container fluid class="full-height-container">
    <v-row no-gutters class="custom-flex-container">
      <v-col v-if="!smAndDown" cols="12" md="6" lg="6" class="bg-surface-dark text-center d-flex flex-column align-center justify-center left-col">
        <div class="content-wrapper">
          <h1 class="gradient-text">Welcome to BookByte</h1>
          <p class="quote-text">Discover Endless Knowledge And Unlock Your Potential With Every Page.</p>
        </div>
      </v-col>

      <v-col cols="12" md="6" lg="6" class="d-flex align-center justify-center right-col">
        <v-card class="custom-card mx-auto" elevation="0">
          <div v-if="smAndDown" class="mobile-welcome-section">
            <h1 class="gradient-text">Welcome to BookByte</h1>
            <p class="quote-text">Discover Endless Knowledge And Unlock Your Potential With Every Page.</p>
          </div>

          <v-card-title class="text-center d-flex flex-column align-center justify-center">
            <v-img
              src="/images/book-logo.png"
              :height="smAndDown ? '120px' : '150px'"
              :width="smAndDown ? '120px' : '150px'"
              contain
              class="mx-auto"
            ></v-img>
            <h2 class="font-weight-black">BOOKBYTE</h2>
            <h5>Login</h5>
          </v-card-title>

          <v-card-text class="pt-2">
            <v-divider class="my-3"></v-divider>

            <LoginForm></LoginForm>

            <v-divider class="my-3"></v-divider>

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
.full-height-container {
  height: 100vh;
  display: flex;
  flex-direction: column;
  overflow-y: auto; 
}

.custom-flex-container {
  display: flex;
  flex-wrap: wrap; 
  height: 100vh; 
}

.left-col,
.right-col {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px; 
}

.content-wrapper {
  width: 100%;  
  max-width: 500px; 
}

.gradient-text {
  background: linear-gradient(45deg, #64c0ce, #dd34f3);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-size: 2.5rem; 
}

@media (max-width: 600px) {
  .gradient-text {
    font-size: 2rem;
  }
}

.quote-text {
  font-size: 1rem;
  margin-top: 10px;
  text-align: center;
}

@media (max-width: 600px) {
  .quote-text {
    font-size: 0.8rem;
  }
}

.custom-card {
  width: 100%;
  max-width: 600px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px; 
}

.social-login {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-top: 15px; 
}

.custom-link {
  color: #b39ddb;
}

.custom-link:active, .custom-link:focus {
  color: #b39ddb;
}

.mobile-welcome-section {
  text-align: center;
  margin-bottom: 10px;
}
</style>
