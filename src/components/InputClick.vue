<template >
  <div id="inputclick" class="inputclick">
        <input type="text" v-model="message">
        <button v-on:click="inputclick">submit</button>
  </div>
  <ul v-for="item in lists" v-bind:key="item.id">
      <input type="checkbox" name="checkbox" value="" v-on:click="textdecoration(item.id,item.title)">
      <li :class="{'textli':item.istextli}">{{item.title}}
      <!-- item:{{item}};数组下标:{{index}} -->
      <!-- <button v-on:click="del(item.id,item.title)">删除</button></li> -->
      </li>
      <div v-on:click="del(item.id,item.title)">X</div>
  </ul>

    

</template>
<script>
export default {
    data() {
        return {
            message: "",
            lists: [
                { id: 1, title: "学习", istextli: false },
            ],
            nextTodoId: 2,
        };
    },
    methods: {
        del: function (id, title) {
            var index = null;
            // this.lists.some((item,i)=>{
            //当遍历item的id等于传入item的id，则相当于找到了数组索引的位置i
            //     if(item.id===id){
            //         index=i;
            //         console.log("id="+id+",数组的索引为"+index);
            //         return true;
            //     }
            // })
            index = this.lists.findIndex(item => {
                //当遍历item的id等于传入item的id，则相当于找到了数组索引的位置i
                if (item.id === id) {
                    title = item.title;
                    return true;
                }
            });
            console.log("id=" + id + ",数组的索引为" + index, "删除了" + title);
            this.lists.splice(index, 1);
        },
        inputclick() {
            this.lists.push({
                id: this.nextTodoId++,
                title: this.message,
                textli: false
            });
            this.message = "";
            console.log("button");
        },
        textdecoration: function (id, title) {
            var index = null;
            index = this.lists.findIndex(item => {
                if (item.id === id) {
                    return true;
                }
            });
            //  this.$data.istextli=!this.istextli;
            this.lists[index].istextli = !this.lists[index].istextli;
            console.log("id=" + id + ",数组的索引为" + index, "完成了" + title);
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
ul li{
    list-style: none;
}
.textli{
    text-decoration:line-through;
    /* list-style: none; */
}
ul{
    display: flex;
}
ul div{
    margin-left: 225px;
}
</style>