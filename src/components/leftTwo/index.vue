<template>
<div class="common">
 <div class="title">主井提升</div>
          <div style="height:24vh">
          <div v-for="item in 2" :key="item">
            <div class="firstContainer">
              <div class="img">
                图片
              </div>
              <div style="width:33%">
                  <p>0 0%</p>
                  <p>提示构思</p>
              </div>
                <div style="width:33%">
                  <p>0 0%</p>
                  <p>提示构思</p>
              </div>
                <div style="width:33%">
                  <p>0 0%</p>
                  <p>提示构思</p>
              </div>
          </div>
          </div>
          </div>     
</div>
         
</template>

<script>
export default {

}
</script>
<style lang="scss" scoped>
  .common{
          width:100%;
          height: 27vh;
          background-color:beige !important;
      }
       .title{
         height:4vh;
         color: aqua;
         line-height: 4vh;
         font-size:1.1vw;
      }
      .firstContainer{
        display: flex;
        margin-top: 1vh;
        height:9vh;
        color: red;
        font-size:1.1vw;
        /* background-color: black; */
      }
</style>