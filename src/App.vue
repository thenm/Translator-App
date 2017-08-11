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
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170809T024436Z.ed96144aef01a3f0.cf565bb240ce6807a3b27658fb23e9a65ec43153&lang=pt&text='+text)
      .then((response) => {
        console.log(response);
      });
    }
  }
}
</script>

<style>

</style>
