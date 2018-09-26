<template>
  <div id="app">
   <v-header @get-from-and-to="getFromAndTo" ref="header"></v-header>
   <v-content :propsData="myData" ref="c"></v-content> 
  </div>
  
</template>
<script>
import header from  '@/components/header/Header'
import content from '@/components/content/Content'
function privateData(from, to){
  this.myData.from = from;
  this.myData.to = to;
}
export default{
    data(){
        return {
             myData:{
                    from:'',
                    to:''
                  }
              
            }
        },
  components:{
    'v-content': content,
    'v-header': header
  },

  methods:{
    getFromAndTo(){
      privateData.call(this, this.$refs.header.ifrom,this.$refs.header.ito);
    
    }
  }

};
</script>
<style>
#app{
  display:flex;
  flex-wrap: wrap;
}
</style>
