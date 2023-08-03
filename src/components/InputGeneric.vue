<template>
<!--  NO VUE PODEMOS TER VARIOS NOS RAIZ-->
<!--   NÃO PRECISAMOS ASSOCIAR UMA LABEL, COM UM INPUT-->
<!--  PRA TORNAMOS ESSE INPUT GENERICO-->
<!--  RECEBEMOS POR VIA PROPS A LABEL E O TIPO DO VALOR-->
<!-- AQUI NÃO PRECISAMOS ASSOCIA RA V-MODEL-->
<!--  SO REALIZAMOS UM EVENTO PRO COMPONENTE PAI QUE HOUVE A MUDANÇA DE VALOR-->
<!--  E ENVIAMOS O TARGET VALUE PRA ELE-->
<!--  NO VUE 3 TODOS OS V MODEL EXIGEM QUE O COMPONENT GENERICO ENVIE UM MODEL VALUE-->
<!--  INDEPENDENTE DO TIPO DE ENTRADA DO COMPONENTE-->
  <label v-if="label">{{ label }}</label>
  <input
      v-bind="$attrs"
      :value="modelValue"
      :placeholder="label"
      @input="$emit('update:modelValue', $event.target.value)"
      class="field"
  >
<!--  O ENVENTO INPUT OUVINTE QUANDO OCORRER UM VALOR DE ENTRADA-->
<!--  COMO A GENTE TA USANDO MULT RAIZE4S-->
<!--  O VUE NÃO CONSEGUE DESCOBRIR QUAL MODELO VAI RECBEER OS ATRIBUTOS-->
<!--POR ISSO PRECISAMSO DESSE V-BIND ATRIBUTES AI-->
<!--COM ISSO ELEE RECEBE O TYPE DO PAI E A ESTILIZAÇÃO DELE-->
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    }
  }
}
</script>
