<script setup>
import { reactive } from 'vue';
const emit = defineEmits(['adicionar']);

const produto = reactive({
    nome:'',
    preco:''
})

function salvar() {
    if (produto.nome === '') {
        alert("O produto não pode ser vazio");
        return;
    }
    emit('adicionar', produto)
}
</script>

<template>

    <form @submit.prevent="salvar">
        <div>
            <label for="nome">  Nome:</label>
            <input type="text" id="nome" v-model="produto.nome">
        </div>
        <div>
            <label for="preco">  Preco:</label>
            <input type="text" id="preco" v-model="produto.preco">
        </div>
        <button type="submit">Salvar</button>
    </form>

</template>