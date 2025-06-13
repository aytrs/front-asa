<template>
  <v-container class="d-flex flex-column align-center justify-center" style="height: 100vh;">
    <Motion
      class="w-100 d-flex align-center justify-center"
      :initial="{ scale: 0 }"
      :in-view="{ scale: 1 }"
      :in-view-options="{ once: true }"
      :transition="{
        type: 'spring',
        stiffness: 260,
        damping: 20,
        delay: 0.3,
      }"
    >
      <v-card
        class="pa-8"
        elevation="10"
        style="width: 400px; height: 500px;"
      >
        <h1 class="text-center">Login</h1>
        <p class="text-center">Por favor, faça login para continuar.</p>
        <v-form ref="form">
          <v-text-field
            style="margin-top: 30px;"
            v-model="email"
            append-icon="mdi-email-outline"
            outlined
            color="black"
            :rules="emailRules"
            label="E-mail"
            required
            class="rounded-lg"
          ></v-text-field>
          <v-text-field
            v-model="password"
            color="purple"
            :rules="passwordRules"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            @click:append="show1 = !show1"
            :type="show1 ? 'text' : 'password'"
            label="Password"
            outlined
            required
            class="rounded-lg"
          ></v-text-field>
          <v-btn append-icon="mdi-login-variant" color="primary" block class="mt-4" @click="$router.push('/alunos')">Entrar </v-btn>
        </v-form>
      </v-card>
    </Motion>
  </v-container>
</template>

<script>
import { Motion } from 'motion-v'

export default {
  components: { Motion },
  data: () => ({
    title: "Login",
    valid: true,
    show1: false,
    email: "",
    emailRules: [
      v => !!v || "E-mail é obrigatório",
      v => /.+@.+\..+/.test(v) || "E-mail deve ser válido"
    ],
    password: "",
    passwordRules: [
      v => !!v || "Senha é obrigatória",
      v => (v && v.length >= 8) || "Senha deve ter pelo menos 8 caracteres"
    ]
  }),
  methods: {
    validate() {
      this.$refs.form.validate();
    },
    onLogin() {
      if (this.$refs.form.validate()) {
        console.log("Login attempt:", this.email, this.password);
      }
    }
  }
};
</script>