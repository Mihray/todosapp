<template >
  <div id="inputclick" class="inputclick">
        <input type="text" v-model="message">
        <button v-on:click="inputclick">submit</button>
  </div>
  <ul v-for="item in lists" v-bind:key="item.id">
    <li>{{item.title}}
    <!-- item:{{item}};数组下标:{{index}} -->
    <button v-on:click="del(item.id)">删除</button></li>
  </ul>
</template>
<script>
export default {
    data(){
        return{
            message:'',
            lists:[
                {id:1,title:'学习'},
            ],
            nextTodoId:2
        }
    },
  methods: {
    del:function(id){
        var index=null;
        // this.lists.some((item,i)=>{
            //当遍历item的id等于传入item的id，则相当于找到了数组索引的位置i
        //     if(item,id===id){
        //         index=i;
        //         console.log("id="+id+",数组的索引为"+index);
        //         return true;
        //     }
        // })
        index=this.lists.findIndex(item=>{
            //当遍历item的id等于传入item的id，则相当于找到了数组索引的位置i
            
            if(item.id===id)
            return true;
        })
        console.log("id="+id+",数组的索引为"+index);
        this.lists.splice(index,1)
    }
    ,
    inputclick(){
        this.lists.push({
            id:this.nextTodoId++,
            title:this.message
        })
        this.message=''
        console.log('button')
    }
  },
}
</script>
<style scoped>
.inputclick{
        display: flex;
        justify-content: center;
        /* align-items: center; */
}
.inputclick input{
    outline:none;
    /* position: absolute; */
    margin-top: 50px;
    margin-right: 10px;
    /* display:block; */
    width: 200px;
    border-top:none ;
    border-right: none;
    border-left: none;
    background-color: rgb(240,240,240);
    border-bottom: 3px dashed rgb(251,182,177);
}
.inputclick button{
    margin-top: 50px;
    width: 50px;
    height:25px;
    border: 1px solid rgb(64,37,40);
    box-shadow: 2px 2px rgb(64,37,40); 
}
</style>