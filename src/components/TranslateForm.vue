<template>
    <div id="TranslateForm">
      <form v-on:submit="formSubmit">
        <input type="text" placeholder="请输入你要翻译的内容" v-model="input">
        <select v-model="value">
          <option value="en">英语</option>
          <option value="ja">日语</option>
        </select>
        <input type="submit" value="翻译">
      </form>

    </div>
</template>

<script>
    export default {
        name: "TranslateForm",
      data(){
          return{
              input:'',
            value:''
          }
      },
      methods:{
        formSubmit:function (e) {
          this.$emit('Tranlate',this.input,this.value);
          e.preventDefault();
        }
      }
    }
</script>

<style scoped>

</style>
