<template>
  <v-container class="d-flex flex-column align-center justify-center" style="height: 100vh; margin-top: 10%;">
    <v-row>
      <v-col cols="12" class="d-flex justify-center">
        <v-card
          class="pa-8"
          elevation="10"
          style="max-width: 500px; width: 100%; height: 500px;"
        >
          <h1 class="text-center">Login</h1>
          <p class="text-center">Por favor, faça login para continuar.</p>
          <v-form>
            <v-text-field label="Email" type="email" style="width: 100%; margin-top: 20%;" required></v-text-field>
            <v-text-field label="Senha" type="password" style="width: 100%;" required></v-text-field>
            <v-btn color="primary" block class="mt-4" @click="$router.push('/alunos')">Entrar</v-btn>
          </v-form>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>