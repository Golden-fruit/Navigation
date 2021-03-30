<template>
<div id="box">
<div><h1>小驿站</h1>
</div>
    <div id="menu">
        <ul >
            <li v-for="(item,index) in list" 
            :key="index" class="lis" 
            @click="menu(index+1)">
            <a> {{item}} </a>
            </li>
        </ul>
    </div>
    <div><form action="php/" method="post">
        <input type="text" placeholder="输入关键字"> 
        <input type="submit" value="search">
        </form>
    </div>
</div>
</template>
<script>
import Msg from './msg.js'
export default {
    data(){
        return {
            list:['A类','B类','C类','D类','E类']
        }
    },
    methods:{
        menu(val){
            //console.log('序列',val)
            Msg.$emit('val',val)
        }
    },mounted(){
        // this.$nextTick(()=>{
        //     var ls=document.getElementsByClassName('lis')
        //     for (let i=0;i<ls.length;i++) {
        //         ls[i].style.display="inline"
        //         ls[i].style.width="60px"
        //     }
        // })
    }
}
</script>>
<style>
#box{
    display: flex;
    justify-content: space-between;
    padding:0 140px;
}
#menu{
    text-align: center;
}
#menu ul{
    list-style: none;
}
#menu li{
    display: inline;
    margin: 0 10px;
    width: 50px;

}
#menu a{
    padding: 20px 20px;
}
#menu a:hover{
    cursor: pointer;
    background-color:#282828;
    border-bottom: white 2px solid;
}
</style>