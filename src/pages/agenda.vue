<template>
    <div>
    <v-spacer />
    <v-toolbar flat color="none">
        <v-toolbar-title class="text-h6">Agenda</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn color="primary" @click="$router.push('/agenda/novo')">
            <v-icon>mdi-plus</v-icon> Novo Evento
        </v-btn>
    </v-toolbar>
    <Calendario />
    </div>
</template>