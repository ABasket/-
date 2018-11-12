<template>
  <div id="app">
    <p>在线翻译</p>
    <TranslateForm @Tranlate="tranInput"></TranslateForm>
    <TranslateOutput v-text="output"></TranslateOutput>
  </div>
</template>

<script>
  import TranslateForm from './components/TranslateForm'
  import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'app',
  data(){
    return{
      output:""
    }
  },
  components:{
    TranslateForm,
    TranslateOutput

  },
  methods:{
    tranInput(output,value){
      this.$http.get("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181112T122659Z.1e254bd6622d8e4c.8a3066993a031267134ec26a0a3b862898452e55&lang="+value+"&text="+output)
        .then((res)=>{
        this.output=res.body.text[0];
      });
      // console.log(data);
    }
  }
}
</script>

<style>

</style>
