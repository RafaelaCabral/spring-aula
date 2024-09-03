<template>
    <div>
        <p> {{ usuario.nome }}</p>
        <p> {{ usuario.senha }}</p>
        <p> <input type="text" v-model="usuario.nome"> </p>
        <p> <input type="text" :value="usuario.senha" @input="senhaMudou"> </p>
        <table>
            <thead>
                <th>Id</th>
                <th>Nome</th>
            </thead>
            <tbody>
                <tr v-for='usuario in usuarios' :key="usuario.id">
                    <td>{{usuarios[0].id}}</td>
                    <td> {{usuarios[0].nome}}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
const usuario = ref({ id: 1, nome: 'teste', senha: '123' });

const usuarios = ref({ id: 1, nome: 'teste', senha: '123' }, { id: 2, nome: 'teste2', senha: '123' });

function senhaMudou(event: any) {
    usuario.value.senha = event.target.value

}
</script>