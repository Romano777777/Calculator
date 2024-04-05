<template>
    <div>
        <v-text-field
            v-model="value1"
            label="valor1"
        ></v-text-field>
        <v-text-field
            v-model="value2"
            label="valor2"
        ></v-text-field>
        <v-btn @click="Calc('soma')">
            Soma
            
        </v-btn>
        <v-btn @click="Calc('subtração')">
            Subtração

        </v-btn>
        <v-btn @click="Calc('multiplicação')">
            Multiplicação

        </v-btn>
        <v-btn @click="Calc('divisão')" >
            Divisão

        </v-btn>
        <div>
            {{result}}
        </div>
    </div>
</template>

<script>
    import { defineComponent } from 'vue'

    export default defineComponent({ 
        data() {
            return {
                result: null, 
               value1: null, 
               value2: null
            }
        },
        mounted() {
            console.log('carregando Romano dawdhawuudwa')
        },
        methods: {
            Calc(operacao) {

                if (operacao === 'soma') return this.result = Number(this.value1) + Number(this.value2)
                if (operacao === 'subtração') return this.result = Number(this.value1) - Number(this.value2)
                if (operacao === 'multiplicação') return this.result = Number(this.value1) * Number(this.value2)
                if (operacao === 'divisão') return this.result = Number(this.value1) / Number(this.value2)
                
            }
            

        }
    })

</script>

<style>

</style>