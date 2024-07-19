<script setup>
//defineProps(['produtos']);
defineProps({
    produtos: {
        type: Array,
        required: true
    }
})
</script>
<template>
    <table>
        <thead>
            <tr>
                <th>id</th>
                <th>nome</th>
                <th>preço</th>
                <th>ações</th>
            </tr>
        </thead>

        <body>

            <tr v-for="produto in produtos" :key="produto.id">
                <td>{{ produto.id }}</td>
                <td>{{ produto.nome }}</td>
                <td>{{ produto.preco }}</td>
                <td><i class="mdi mdi-delete" @click="$emit('excluir', produto.id)"></i></td>

            </tr>

        </body>
    </table>
    <button @click="$emit('apagarTudo')">excluir tudo</button>
</template>