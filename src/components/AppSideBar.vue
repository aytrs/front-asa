<!-- eslint-disable vue/html-indent -->
<template>
  <v-card>
      <v-navigation-drawer
        expand-on-hover
        rail
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
            subtitle="sandra_a88@gmailcom"
            title="Sandra Adams"
          ></v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-account-school" title="Alunos" value="alunos" @click="$router.push('alunos')"></v-list-item>
          <v-list-item prepend-icon="mdi-account-multiple" title="Shared with me" value="shared"></v-list-item>
          <v-list-item prepend-icon="mdi-star" title="Starred" value="starred"></v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-app>
        <v-app-bar app>
          <v-toolbar-title>Ensino ASA</v-toolbar-title>
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