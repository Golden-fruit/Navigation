<template>
<div>
    <div>
       <Girl :girlId="kk"></Girl>
    </div>

</div>
</template>
<script>
import Msg from './msg.js'
import Girl from './Girl.vue'
export default {
    data(){
        return{
            kk:0,
            list:['A','B','C','D','E']
        }
    },
    components:{
        Girl
    },
    mounted(){
        var _this=this
        Msg.$on('val',m=>{
            _this.kk=m
        })
    }
}
</script>>