<template>
    <div id="painelLancamento">
        <div id="formularioLancamento">

            <form>
                <div id="tiposLancamentos">
                    <input type="radio" name="tipo" id="entrada">
                    <label for="entrada">Entrada</label>

                    <input type="radio" name="tipo" id="saida">
                    <label for="saida">Saída</label>
                </div>


                <label for="valor">Valor</label>
                <input type="number" name="valor" id="valor">

                <label for="descricao">Descrição</label>
                <input type="text" name="descricao" id="descricao" value="">

                <label for="data">Data</label>
                <input type="date" name="data" id="data">

                <button>Lançar</button>
            </form>
        </div>

        <div id="areaLancamentos">
            <BlocoLancamento 
                tipo="entrada" 
                :lancamento="{
                    descricao: 'Venda de HQ',
                    data: '2026-09-10',
                    valor: 100,
            }" />

                <BlocoLancamento 
                tipo="saida" 
                :lancamento="{
                    descricao: 'Venda de HQ',
                    data: '2026-09-10',
                    valor: 50,
            }" />

                <BlocoLancamento 
                tipo="entrada" 
                :lancamento="{
                    descricao: 'Venda de HQ',
                    data: '2026-09-10',
                    valor: 100,
            }" />

        </div>
    </div>
</template>

<script setup lang="ts">
import BlocoLancamento from './BlocoLancamento.vue'

</script>

<style scoped>
#painelLancamento {
    width: 40%;
    padding: 20px;
}

#formularioLancamento {
    background-color: white;
    border-radius: 20px;
    padding: 20px;
    font-family: "padrao";
}

#valor,
#descricao,
#data,
button {
    display: block;
    margin-bottom: 10px;
}


#valor,
#descricao,
#data {
    height: 20px;
    font-family: "padrao";
    font-size: 100%;
}

#tiposLancamentos {
    margin-bottom: 10px;
    font-family: "negrito";
}

#tiposLancamentos label {
    margin-right: 20px;
}

#tiposLancamentos label:first-of-type {
    color: #22a7f0;
}

#tiposLancamentos label:last-of-type {
    color: #e74c3c;
}

#descricao {
    width: 70%;
}

button {
    background-color: var(--cor-destaque);
    border: none;
    outline: none;
    border-radius: 5px;
    padding: 10px 20px;
    color: white;
    font-family: "negrito";
    font-size: 120%;
}

#areaLancamentos {
    margin-top: 30px;
}

</style>