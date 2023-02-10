<template>
   <div class="wapper">
           <div class="wapperBody">
            <div v-for="item in 8" :key="item">
              <div class="menu">{{ item }}</div>
            </div>
           </div> 
       </div>
</template>

<script>
export default {

}
</script>
<style lang="scss" scoped>
     .wapper{
      height: 100%;
      width:100%;
      display: flex;
      flex-direction: row-reverse;
     }
     .wapperBody{
      margin-bottom: 3vh;
      display: flex;
      flex-direction: column-reverse;
     }
     .menu{
      margin-right: 3vh;
      width:5vh;
      height: 5vh;
      line-height: 5vh;
      text-align: center;
      margin-top: 0.2vh;
      background-color: darkcyan;
     }
</style>