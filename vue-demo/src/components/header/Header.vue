<template id="header" >
   <div class="header">
      <p>From :</p>
       <input type="text" v-model="ifrom" name="From">
       <p>To :</p>
       <input  type="text" v-model="ito" name="To">
     <button type="button" @click="getFromAndTo">Go!</button>
   </div>
</template>

<script>
export default{
 name: 'Header',
  data(){
        return {
            ifrom: '',
            ito:''
            }
        },
    methods:{
      getFromAndTo(){
          this.$emit('get-from-and-to');
      }
    
  }
};

</script>
<style>
.header{
 display: flex;
 width: 100%;
 margin:50px auto;
 justify-content: center;
 margin-bottom: 10px;
 background: #CCFFFF;
 margin-top: 10px;
}
p{
  margin-right: 10px;
   font-family: "STHupo", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
   color: #CC0000;

}
input{
  margin:10px 10px 10px 0px;
  border-radius:10px;
   background: #FFFF00;
   border:none;
    font-family: "STHupo", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
}
button{
  margin:10px 10px 10px 0px;
   font-weight: 300;
  font-size: 6px;
  font-family: "STHupo", "Helvetica Neue", Helvetica, Arial, "Lucida Grande", sans-serif;
   border: none;
   background: #FFFF00;
    color: #CC0000;
   border-radius:10px;
  

}

</style>
