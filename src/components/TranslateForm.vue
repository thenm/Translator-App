<template>
  <div id="translateForm">
    <form v-on:submit="formSubmit">
      <input type="text" v-model="textToTranslate" placeholder="Enter the text to translate">
      <input type="submit" value="Translate">
    </form>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data () {
    return {
      textToTranslate:''
    }
  },
  methods:{
   formSubmit(e){
    //  alert(this.textToTranslate);
     this.$emit('formSubmit', this.textToTranslate);
     e.preventDefault();
   }
  }
}
</script>

<style scoped>

</style>
