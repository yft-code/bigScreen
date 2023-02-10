<template>
   <div
    :style="{
      'transformOrigin':'center top',
      'transform':`scale(${rate},${rate})`,
      '-webkit-transform':`scale(${rate},${rate})`,
      '-moz-transform':`scale(${rate},${rate})`,
      '-o-transform':`scale(${rate},${rate})`,
      '-ms-transform':`scale(${rate},${rate})`
    }"
    >
    <div class="title">
        <div class="left">left</div>
        <div class="center">center</div>
        <div class="right">right</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Login",
  data(){
return{
	rate:1
   }
},
mounted() {
    this.resize_window()
    window.addEventListener('resize', () => {
      this.resize_window()
    })
  },
destroyed() {
  window.removeEventListener('resize', () => {
    this.resize_window()
  })
},
methods: {
	//在这里发送页面的请求获取大屏展示的数据
    async initialize() {
      try {
        this.loading = true
        this.$emit('pageLoading', true)
      } catch (err) {
        console.log(err)
      } finally {
        setTimeout(() => {
          this.loading = false
          this.$emit('pageLoading', false)
        }, 3000)
      }
    },
    resize_window() {
      const heightRatio = Number(document.documentElement.clientHeight / 1080)
      const widthRatio = Number(document.documentElement.clientWidth / 1920)
      var ratio= document.documentElement.clientWidth /document.documentElement.clientHeight
      if (ratio< 1920 / 1080) {
        this.rate= widthRatio 
      } else {
        this.rate= heightRatio 
      }
    }
  }
}

</script>
<style lang="scss" scoped>
.title{
  display: flex;
  // width: 100%;
  height: 100vh;
  
}
.right,.left{
 height: 100%;
 width: 100px;
 background-color: aqua;
}
.center{
  flex: 1;
  height: 100%;
  background-color: blanchedalmond;
}
</style>
