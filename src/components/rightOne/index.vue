<template>
  <div class="common">
    <div class="title" style="">人员定位</div>
    <div class="innerContainer">
      <div v-for="item in 3" :key="item">
        <div class="inner">
          <div class="imgContainer">
            <img class="imgs" src="@/assets/img/index/tools.png" alt="" />
          </div>
          <div class="innerTitle">
            <div>人dd</div>
            <div class="demoTop">
              <div>211</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
.common {
  width: 100%;
  height: 27vh;
  background-color: beige;
}
.title {
  height: 4vh;
  font-size: 1.1vw;
}
.innerContainer {
  display: flex;
  margin: 0 1.4vw;
  justify-content: space-around;
  height: 23vh;
  align-items: center;
}
.inner {
  display: flex;
  height: 10vh;
}
.rightTitle {
  font-size: 1.1vw;
}
.imgContainer {
  // width: 50%;
  min-width:10%;
  max-width:50%;
  height: 10vh;
  /* background-color: aqua; */
}
.imgs {
  width: 100%;
  height: 100%;
}
.demoTop {
  display: flex;
  flex-direction: column-reverse;
}
.innerTitle {
  display: flex;
  flex-direction: column;
  font-size: 1.1vw;
}
.innerTitle > div {
  flex: 1;
}
</style>