<script setup>
import LoginForm from '@/components/auth/LoginForm.vue'
</script>

<template>
  <v-container fluid class="full-height-container">
    <!-- Custom class for flexbox to keep side-by-side layout on all screen sizes -->
    <v-row no-gutters class="custom-flex-container">
      <!-- Left side with welcome message and quote -->
      <v-col cols="12" xs="6" md="6" lg="6" class="bg-surface-dark text-center d-flex flex-column align-center justify-center">
        <h1 class="gradient-text">Welcome to Bookbyte</h1>
        <p class="quote-text">Discover endless knowledge and unlock your potential with every page.</p>
      </v-col>

      <!-- Right side with login form -->
      <v-col cols="12" xs="6" md="6" lg="6" class="d-flex align-center justify-center">
        <v-card class="custom-card mx-auto" elevation="0">
          <v-card-title class="text-center d-flex flex-column align-center justify-center">
            <v-img
              src="/images/book-logo.png"
              :height="150"
              :width="150"
              contain
              class="mx-auto"
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
/* Ensure the full height for mobile layouts */
.full-height-container {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

/* Custom Flexbox styles to prevent stacking on mobile */
.custom-flex-container {
  display: flex;
  flex-direction: row !important; /* Force row direction even on small screens */
  flex-wrap: nowrap;              /* Prevent wrapping */
  height: 100vh;                  /* Ensure both sides take up full height */
}

/* Gradient text for the welcome message */
.gradient-text {
  background: linear-gradient(45deg, #64c0ce, #dd34f3);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-size: 3rem;
}

/* Media query for mobile font size adjustment */
@media (max-width: 600px) {
  .gradient-text {
    font-size: 2rem;
  }
}

/* Quote text styling */
.quote-text {
  font-size: 1rem;
  margin-top: 15px;
}

/* Media query for mobile quote text adjustment */
@media (max-width: 600px) {
  .quote-text {
    font-size: 0.8rem;
  }
}

/* Custom card styling */
.custom-card {
  width: 100%;
  max-width: 700px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px;
}

.custom-link {
  color: #b39ddb;
}

.custom-link:active, .custom-link:focus {
  color: #b39ddb;
}
</style>
