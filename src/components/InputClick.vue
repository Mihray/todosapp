<template >
  <div id="inputclick" class="inputclick">
        <input type="text" v-model="message">
        <button v-on:click="inputclick">submit</button>
  </div>
  <ul>
    <li v-for="(item, index) in lists" v-bind:key="item.id">item:{{item}};数组下标:{{index}}
    <button v-on:click="delete(item)">删除</button></li>
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
    delete(i){
        this.lists.filter(function(){

        })
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