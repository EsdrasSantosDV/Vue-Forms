<template>
<!--  RECEBEMOS A LABEL NORMALMENTE-->
  <label v-if="label">{{ label }}</label>
  <select
      class="field"
      :value="modelValue"
      v-bind="{
      ...$attrs,
      onChange: ($event) => { $emit('update:modelValue', $event.target.value) }
    }"
  >
<!--    COMO ESTAMOS USANDO MULTI NOS, FIZEMOS O BIND USANDO OS ATRIBUTOS-->
<!--     E DA MESMA FORMA PRECISAMOS EMITIR O INPUT PRO PAI USANDO O MODEL VALUE -->
<!--  ENVIANDO O TARGET VALUE-->
<!--    AQUI RECEBMOS AS OPÇOEES POR PROPS TBM-->
<!--    E FUNCIONA IGUAL LA NO ANGULAR NO TEMPLATE DRIVEN FORMS-->
<!--    O SELECECIOANDO E IGUAL O MODEL VALUE-->
    <option
        v-for="option in options"
        :value="option"
        :key="option"
        :selected="option === modelValue"
    >{{ option }}</option>
  </select>
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
    },
    options: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

</style>
