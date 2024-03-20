<script setup>
    const props = defineProps(['primeiroCampo', 'selecionaOperacao', 'segundoCampo'])
</script>

<template>
    <div class="row">
        <div class="col-5">
            <input @keyup="props.primeiroCampo" type="number" class="form-control text-center" id="num1" placeholder="Primeiro número">
        </div>
        <div class="col-2 ps-0 pe-0">
            <select @change="props.selecionaOperacao" class="custom-select form-control text-center" id="operation">
                <option value="add">+</option>
                <option value="subtract">-</option>
                <option value="multiply">*</option>
                <option value="divide">/</option>
            </select>
        </div>
        <div class="col-5">
            <input @keyup="props.segundoCampo" type="number" class="text-center form-control" id="num2" placeholder="Segundo número">
        </div>
    </div>
</template>