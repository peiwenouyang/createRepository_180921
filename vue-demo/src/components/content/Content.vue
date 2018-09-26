<template>
    <div class="content" ref="content">

    </div>
</template>
<script>
function worker(input ){
	var from = Number(input.from);
	var to = Number(input.to);
	var list;
	if(from != null && to != null && from > 0 && to > 0 && from <= to)
	{
		 list = "";
		 var box = "";
		  do{
            if (from%3 == 0 && from%5 != 0)
            {
                box = '<div align="center" style="float:left; width:60px;hight:30px;background: #66FF66; border-width: 2px 2px 2px 2px;margin:2px 2px 2px 2px;border-radius:10px;">Fizz</div>';
            }
            if (from%3 != 0 && from%5 == 0)
            {
                 box = '<div align="center" style="float:left; width:60px;hight:30px; background: #FFFF33; border-width: 2px 2px 2px 2px;margin:2px 2px 2px 2px;border-radius:10px;">Buzz</div>';
            }
            if (from%3 == 0 && from%5 == 0)
            {
                box = '<div align="center" style="float:left; width:60px;hight:30px; border-style: solid;border-color: #FF0000; border-width: 2px 2px 2px 2px;margin:2px 2px 2px 2px;border-radius:10px;">FizzBuz</div>';
            }
            if (from%3 != 0 && from%5 != 0)
            {
                box = '<div align="center" style="float:left; width:60px;hight:30px;margin:2px 2px 2px 2px;">'+from+'</div>';
            }
            list += box;
            from++;
        }while ( from <= to );
    }
	return list;
}
function show(output){
	        this.$refs.content.innerHTML = null;
		if(output != null )
		{
			this.$refs.content.innerHTML = output;
	    }
}


export default{
 name: 'Content',
 props:{
 	propsData:Object
 },
 watch: {
       propsData: {
					  handler(newVal) 
					  {
							  this.myWorker = this.$worker.run(worker,[newVal])
							  .then(result => {
							  	show.call(this,result);
								    });
						

					  },
		 			  immediate: true,
		 			  deep: true
		      }
		}

};
</script>
<style>
.content{
	margin-top: 0px;
	 display: flex;
	 flex-wrap: wrap;
	 padding: 1px 1px 1px 1px;
	 background: #CCFFFF;

}
</style>
