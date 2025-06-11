<!-- eslint-disable vue/html-indent -->
<template>
  <v-card>
      <v-navigation-drawer
        expand-on-hover
        rail
      >
        <v-list>
          <v-list-item
            prepend-avatar=""
            subtitle="exemplo@exemplo.com"
            title="Exemplo Usuário"
          ></v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-account-school" title="Alunos" value="alunos" @click="$router.push('alunos')"></v-list-item>
          <v-list-item prepend-icon="mdi-calendar" title="Agenda" value="agenda" @click="$router.push('agenda')"></v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-app>
        <v-app-bar app>
          <v-toolbar-title><a href="/" style="text-decoration: none; color: #000;">Ensino ASA</a></v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn text @click="$router.push('/')">Temas</v-btn>
          <v-btn @click="logout">Logout</v-btn>
        </v-app-bar>

        <v-main>
          <router-view />
        </v-main>
      </v-app>
  </v-card>
</template>