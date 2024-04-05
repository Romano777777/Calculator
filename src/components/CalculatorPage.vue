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

        <div class="container-result">
            {{result}}
        </div>

        <div class="operation-container">
            <div class="operation-item" :class="{'operation-active':operation === 'soma'}" @click="Calc('soma')" >
                <v-icon icon="mdi-plus" size="80" ></v-icon>
                <span>Somar</span>
            </div>
            <div class="operation-item" :class="{'operation-active':operation === 'subtração'}"  @click="Calc('subtração')">
                <v-icon icon="mdi-minus" size="80" ></v-icon>
                <span>Subtração</span>
            </div>
            <div class="operation-item" :class="{'operation-active':operation === 'multiplicação'}" @click="Calc('multiplicação')">
                <v-icon icon="mdi-multiplication" size="80" ></v-icon>
                <span>Multiplicação</span>
            </div>
            <div class="operation-item" :class="{'operation-active':operation === 'divisão'}" @click="Calc('divisão')">
                <v-icon icon="mdi-division" size="80" ></v-icon>
                <span>Divisão</span>
            </div>
        </div>

            
        </div>
</template>

<script>
    import { defineComponent } from 'vue'

    export default defineComponent({ 
        data() {
            return {
                operation: null,
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
                this.operation = operacao

                if (operacao === 'soma') return this.result = `${this.value1} + ${this.value2} = ${Number(this.value1) + Number(this.value2)} `
                if (operacao === 'subtração') return this.result = `${this.value1} - ${this.value2} = ${Number(this.value1) - Number(this.value2)} `
                if (operacao === 'multiplicação') return this.result = `${this.value1} x ${this.value2} = ${Number(this.value1) * Number(this.value2)} `
                if (operacao === 'divisão') return this.result = `${this.value1} / ${this.value2} = ${Number(this.value1) / Number(this.value2)} `
                
            }
            

        }
    })

</script>

<style lang="scss" >
@import url('https://fonts.googleapis.com/css2?family=Aclonica&family=Advent+Pro:ital,wght@0,100..900;1,100..900&family=Tilt+Neon&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Aclonica&family=Advent+Pro:ital,wght@0,100..900;1,100..900&family=Tac+One&family=Tilt+Neon&display=swap');

.operation-container {
    padding: 0px 50px;
    display: flex;
    justify-content: space-between;

    .operation-item {
        cursor: pointer;
        font-family: "Tilt Neon", sans-serif;
        font-size: 26px;
        flex-direction: column;
        justify-content: center;
        display: flex;
        align-items: center;
        border-radius: 10px;
        width: 250px;
        height: 200px;
        background-color: #659FA6;
        &:hover {
            background-color: #6aa2a8;
        }
    }
    .operation-active {
        background-color: #308C83;
    }
}

.container-result { 
    margin-bottom: 50px;
    color: #155952;
    font-size: 120px;
    font-family: "Tac One", sans-serif;
    justify-content: center;
    display: flex;
    align-items: center;
    width: 100%;
    height: 400px;
    background-color: #B4D9CE;
}


</style>