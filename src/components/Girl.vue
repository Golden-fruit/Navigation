<template>
    <div name="show">
        <ul id="girl">
            <li  v-for="(girl,index) in list" :key="index">
                <img v-bind:src="girl.src">
                <p>{{girl.name}} </p>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:"show",
    data(){

        return{
            list:[]
        }
    },
    methods:{
        get(url="json/img5.json"){
            var _this=this;
            this.$http.get(url).then(res=>{
            _this.list=res.data
            })
        }
    },
    mounted(){
        this.get()
    },
    props:{
        girlId:Number
    },
    watch:{
        girlId(){
            var obj=this;
            var url='';
            if (obj.girlId==1) {
                url='json/img.json'
            }else{
                url='json/img'+this.girlId+'.json'}
                //console.log('id',this.girlId)
            this.get(url)
        }
    }
}
</script>
<style>
#girl{
    margin: 20px auto;
}
#girl li{
    width: 260px;
    height: 260px;
    list-style: none;
    float: left;
    margin-left: 35px;
    margin-bottom: 20px;
}
#girl img{
    width: 255px;
    height: 250px;
}
</style>