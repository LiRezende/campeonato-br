<template>
    <v-container>
        <h2 class="text-h5 text-center mb-3 mt-5">
            Classificação
        </h2>
        <template>
            <v-simple-table>
                <template v-slot:default>
                <thead>
                    <tr>
                    <th class="text-center">
                        Posição
                    </th>
                    <th class="text-center">
                        Clubes
                    </th>
                    <th class="text-center">
                        Pontuação
                    </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(clube, index) of clubesLista" :key="clube.id">
                        <td class="text-center">{{ index + 1 }}</td>
                        <td class="text-center">
                            <v-avatar size="24"> 
                                <img
                                    :src="clube.escudo"
                                    :alt="clube.nome"
                                >
                            </v-avatar>
                            <span class="pl-3">{{ clube.nome }}</span>
                        </td>
                        <td class="text-center">{{ clube.pontos }}</td>
                    </tr>
                </tbody>
                </template>
            </v-simple-table>
        </template>
        
    </v-container>
    
</template>

<script>
export default {
    name: 'ClubesLista',
    data() {
        return {
            clubesLista: []
        }
    },
    created() {
        fetch('https://hackthon-decola.firebaseio.com/clubes-lista.json')
            .then(resposta => resposta.json())
            .then(json => {
                this.clubesLista = json
            });
            
    }
}
</script>

<style scoped>

</style>