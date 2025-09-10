<script setup>
</script>

<template>
    <div class="container p-4">
        <header class="p-4 mb-4 mt-4 rounded-3">
            <h1>Caculadora Aritmética</h1>
        </header>
        <form>
            <div class="row mb-4">
                <div class="col">
                    <div class="row">
                        <div class="col mb-3">
                            <input type="number" placeholder="Digite o primeiro valor:" class="form-control"></input>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col mb-3">
                            <input type="number" placeholder="Digite o segundo valor:" class="form-control"></input>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col mb-3">
                            <select name="" id="" class="form-control">
                                <option value="adicao">Adição +</option>
                                <option value="adicao">Subtração -</option>
                                <option value="adicao">Multiplicação *</option>
                                <option value="adicao">Divisão /</option>
                            </select>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="container container_screen p-3">
                        10 + 10 = 20
                    </div>
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
        background-color: #0c2461;
        
    }

    .container_screen {
        background-color: #079992;
        max-height: 145px;
        height: 100%;
    }
</style>
