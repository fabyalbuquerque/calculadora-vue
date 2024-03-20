<script setup>
  const props = defineProps(['calculater']);
</script>

<template>
  <div class="row mt-4">
    <div class="col">
      Resultado:
    </div>
    <div class="col">
      {{props.calculater}}
    </div>
  </div>
</template>