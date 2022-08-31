<template>
      <input type="checkbox" name="checkbox" value="" v-on:click="textdecoration(id, title)">
      <li :class="{'textli':istextli}">{{title}}
      <!-- item:{{item}};数组下标:{{index}} -->
      <!-- <button v-on:click="del(item.id,item.title)">删除</button></li> -->
      </li>
      <div v-on:click="del(id, title)">X</div>
</template>

<script>
export default {
    props:{
        id:String,
        title:String,
        istextli:Boolean,
    },
    data(){
        return {
        }
    },
    methods:{
          del:function(id,title){
            // 告诉父组件删除了
            
        
    }
    ,
    inputclick(){
        this.lists.push({
            id:this.nextTodoId++,
            title:this.message,
            textli:false
        })
        this.message=''
        console.log('button')
    },
    textdecoration:function(id,title){
        var index=null;
        index=this.lists.findIndex(item=>{
            if(item.id===id){
                return true;
            }
        })
            //  this.$data.istextli=!this.istextli;
                this.lists[index].istextli = !this.lists[index].istextli; 
             console.log("id="+id+",数组的索引为"+index,"完成了"+title);
    }
  },
}
</script>

<style scoped>

</style>