<template>
    <div class="blocoLancamento">
        <div class="botoes">

            <img v-if="props.tipo === 'entrada'" src="../img/mais.png" alt="Entrada" class="imagemLancamento">

            <img v-else if="props.tipo === 'saida'" src="../img/menos.png" alt="Saída" class="imagemLancamento">

            <button class="botaoRemover">
                <img src="../img/lixeira.png" alt="Remover Lançamento">
            </button>
        </div>

        <div class="descricaoLancamento">
            <span 
            v-if="tipo === 'entrada'" 
            class="valor entrada">
            R$ {{ lancamento?.valor?.toLocaleString(undefined, { minimumFractionDigits: 2, maximumFractionDigits: 2 }) }}
        </span>

           <span 
            v-else-if="tipo === 'saida'" 
            class="valor gasto">
            R$ {{ lancamento?.valor?.toLocaleString(undefined, { minimumFractionDigits: 2, maximumFractionDigits: 2 }) }}
        </span>
        
            <span>{{ new Date(lancamento?.data ?? '').toLocaleDateString('pt-BR', {timeZone: 'UTC'}) }}</span>
            <span>{{ lancamento?.descricao }}</span>
        </div>

    </div>
</template>

<script setup lang="ts">

interface Lancamento {
    valor?: string | number
    data?: string
    descricao?: string
}

interface Props {
    tipo: string
    lancamento: Lancamento
}

const props = defineProps<Props>()

</script>

<style scoped>
.blocoLancamento {
    display: flex;
    background-color: white;
    border-radius: 20px;
    font-family: "padrao";
    padding: 10px;
    margin-bottom: 10px;
}

.botoes {
    width: 50%;
    display: flex;
    align-items: center;
}

.imagemLancamento {
    width: 50px;
    vertical-align: middle;
}

.botaoRemover {
    background-color: white;
    border: none;
    outline: none;

    vertical-align: middle;
}

.botaoRemover:hover {
    cursor: pointer;
}

.botaoRemover img {
    width: 40px;
}

.botaoRemover img:active {
    filter: invert(100%);
}

.descricaoLancamento {
    width: 50%;
    float: right;
    text-align: right;
}

.descricaoLancamento span {
    display: block;
    font-size: 80%;
}

.valor {
    font-family: "negrito";
    font-size: 200% !important;
}

.entrada {
    color: #22a7f0;
}
.gasto {
    color: red;
}

</style>