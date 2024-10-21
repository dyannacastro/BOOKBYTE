<script setup>
import RegisterForm from '@/components/auth/RegisterForm.vue'
import { useDisplay } from 'vuetify'

const { mobile } = useDisplay()
</script>

<template>
      <v-container fluid>
        <v-row>
          <v-col cols="12" lg="6" class="bg-surface-dark h-screen text-center d-flex flex-column align-center justify-center" v-if="!mobile">
            <h1 class="gradient-text">Welcome to Bookbyte</h1>
            <p class="quote-text">-------------------------------------- OR ---------------------------------------</p>

            <div class="social-login">
          <v-btn icon large>
            <v-icon color="red darken-1">mdi-google</v-icon>
          </v-btn>
          <v-btn icon large>
            <v-icon color="blue darken-4">mdi-facebook</v-icon>
          </v-btn>
        </div>
          </v-col>

          <v-col cols="12" lg="6" class="d-flex align-center justify-center" :class="mobile ? '' : 'pt-2 h-screen'">
            <v-card class="mx-auto custom-card" elevation="0" max-width="600">
              <v-card-title class="text-center">
                <v-img
                  src="/images/book-logo.png"
                  :height="mobile ? '200%' : '200'"
                  contain
                ></v-img>
                <h2 class="font-weight-black">BOOKBYTE</h2>
                <h5>Registration</h5>
              </v-card-title>

              <v-card-text class="pt-4">
                <v-divider class="my-5"></v-divider>

                <RegisterForm></RegisterForm>

                <v-divider class="my-5"></v-divider>

                <h4 class="text-center font-weight-black-">
                  Already have an account?
                  <RouterLink to="/" class="custom-link">
                    Log in here
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
  background: linear-gradient(45deg, #64c0ce, #b909fe);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-size: 3rem;
}


.quote-text {
  font-size: 1rem;
  margin-top: 15px; 
}

.custom-card {
  max-width: 700px;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px;
}

.social-login {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 20px; 
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