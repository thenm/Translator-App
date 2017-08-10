<template>
  <div id="app">
    <h1>Word tarnslator</h1>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
export default {
  name: 'app',
  components: {
    TranslateForm
  },
  methods: {
    translateText:function(text) {
      alert(text);
    }
  }
}
</script>

<style>

</style>
