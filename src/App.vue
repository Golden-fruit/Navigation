<template>
    <div id="app">
        <div id="header">
            <Nag></Nag>
        </div>
        <div id="main">
            <Main></Main>
        </div>
        <div id="footer">Copyright©2021 videolib</div>

    </div>
</template>

<script>
import Nag from '@/components/Nag.vue'
import Main from '@/components/Main.vue'
export default {
  name:'app',
  components:{
    Nag,Main
  }
}
</script>>
<style>
*{
  padding:0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
    background-color: #101010;
}
/* for phones */
#inHeader, #main, #footer {
    width: 100%;
}

/* for desktop */
@media only screen and (min-width: 2000px) {
  #inHeader, #main, #footer {
    width: 2000px;
  }
}
#header {
    color: #EEEEEE;
    height: 60px;
    line-height: 60px;
    background-color: #101010;
    top: 0;
    right: 0;
    margin: 0 auto;
    z-index: 10;
}
#main {
    background-color: #202020;
    color: #eee;
    z-index: 9;
    margin: 0px auto;
    height: 570px;
}

#footer {
    color: #eee;
    text-align: center;
    line-height: 60px;
    margin: 0px auto;
    background-color: #282828;
}
</style>
