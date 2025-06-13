<template>
    <v-container>
    <v-data-table>
        <template v-slot:top>
            <v-toolbar flat>
                <v-toolbar-title>Alunos</v-toolbar-title>
                <v-spacer></v-spacer>
                 <v-text-field
                    v-model="search"
                    append-icon="mdi-magnify"
                    label="Pesquisar"
                    single-line
                    hide-details
                    class="ml-4"
                    style="max-width: 300px; width: 100%;" 
                ></v-text-field>
                <v-btn color="primary" @click=addItem(item.id)> <v-icon>mdi-account-plus</v-icon> Novo Aluno</v-btn>
            </v-toolbar>
        </template>

        <template v-slot:item.actions="{ item }">
            <v-btn icon @click="$router.push(`/alunos/${item.id}`)">
                <v-icon>mdi-eye</v-icon>
            </v-btn>
            <v-btn icon @click=editItem(item.id)>">
                <v-icon>mdi-pencil</v-icon>
            </v-btn>
            <v-btn icon @click="$emit('delete', item.id)">
                <v-icon>mdi-delete</v-icon>
            </v-btn>
        </template>

        <template v-slot:no-data>
            <div class="text-center">
                Nenhum aluno encontrado.
            </div>
        </template>

        <!-- Aqui você pode adicionar os dados dos alunos -->
    </v-data-table>
    </v-container>
</template>