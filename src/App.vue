<template>
  <div id="app">
    <h1>Word translator</h1>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
     <!-- translateText is a function which is called on form submit. -->
     <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function() {
    return {
      translatedText: ''
    }
  },
  methods: {
  //  emitted value - this.textToTranslate from TranslateForm component is caught in text
    translateText: function(text, language) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170809T024436Z.ed96144aef01a3f0.cf565bb240ce6807a3b27658fb23e9a65ec43153&lang='+language+'&text='+text)
      .then((response) => {
       this.translatedText = response.body.text[0];
        // the translated word is in the response{} -> body{} -> text array
      });
    }
  }
}
</script>

<style>

</style>
