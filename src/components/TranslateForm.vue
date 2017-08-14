<template>
  <div id="translateForm">
      <form v-on:submit="formSubmit">
        <input type="text" v-model="textToTranslate" placeholder="Enter the text to translate">
        <select v-model="language">
          <option value="bn">Bengali</option>
          <option value="gu">Gujrati</option>
          <option value="hi">Hindi</option>
          <option value="ml">Malayalam</option>
          <option value="mr">Marathi</option>
          <option value="pa">Punjabi</option>
        </select>
        <input type="submit" value="Translate">
      </form>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data () {
    return {
      textToTranslate : '',
      language : ''
    }
  },
  created() {
    this.language = 'bn'
  },
  methods: {
   formSubmit(e){
    //  alert(this.textToTranslate);
     this.$emit('formSubmit', this.textToTranslate, this.language);
    //  textToTranslate is emitted from TranslateForm to App.vue
    // formSubmit can be anything
     e.preventDefault();
   }
  }
}
</script>

<style scoped>

</style>
