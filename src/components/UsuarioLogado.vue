<template>
  <div>
    <h2>Olá, {{nome}}!</h2>
  </div>
</template>

<script>
export default {
  name: 'UsuarioLogado',
  props:{
    nome:{
      type: String,
      required: true
    }
  }
}
</script>
<style></style>
