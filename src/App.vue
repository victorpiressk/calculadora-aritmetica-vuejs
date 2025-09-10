<script setup>
import { reactive } from 'vue';

    const estado = reactive({
        primeiroValor: 0,
        segundoValor: 0,
        operacao: '+',
    })

    const operacaoDeAdicao = () => {
        const soma = parseFloat(estado.primeiroValor) + parseFloat(estado.segundoValor)
        return soma
    }

    const operacaoDeSubtracao = () => {
        return estado.primeiroValor - estado.segundoValor
    }

    const operacaoDeMultiplicacao = () => {
        return estado.primeiroValor * estado.segundoValor
    }

    const operacaoDeDivisao = () => {
        return estado.primeiroValor / estado.segundoValor
    }

    const filtraOperacaoAritmetica = () => {
        switch (estado.operacao) {
            default:
                return operacaoDeAdicao()
            case '-':
                return operacaoDeSubtracao()
            case '*':
                return operacaoDeMultiplicacao()
            case '/':
                return operacaoDeDivisao()
        }
    }
</script>

<template>
    <div class="container p-4">
        <div class="row">
            <header class="col-6 p-4 mb-4 mt-4 rounded-3">
                <h1 class="mb-4">Caculadora Aritmética</h1>
                <div class="container container_screen p-3 rounded-3">
                    {{ estado.primeiroValor }} {{ estado.operacao }} {{ estado.segundoValor }} = {{ filtraOperacaoAritmetica() }}
                </div>
            </header>
        </div>
        <form>
            <div class="row mb-4">
                <div class="col-6">
                    <select @change="evento => estado.operacao = evento.target.value" class="form-control mb-3">
                        <option value="+">Adição +</option>
                        <option value="-">Subtração -</option>
                        <option value="*">Multiplicação *</option>
                        <option value="/">Divisão /</option>
                    </select>
                    <input @keyup="evento => estado.primeiroValor = evento.target.value" type="number" placeholder="Digite o primeiro valor:" class="form-control mb-3"></input>
                    <input @keyup="evento => estado.segundoValor = evento.target.value" type="number" placeholder="Digite o segundo valor:" class="form-control mb-3"></input>
                </div>
            </div>
        </form>
    </div>
</template>

<style scoped>
    .container {
        color: #fff;
    }

    header {
        background-color: #4834d4;
        
    }

    .container_screen {
        background-color: #be2edd;
    }
</style>
