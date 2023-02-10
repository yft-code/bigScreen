<template>
  <div class="largeScreen">
    <!-- 头部 -->
    <indexTop />
    <div class="box">
      <div class="left"></div>
      <div class="center">
        <div class="centerLeft">
          <leftTwo />
          <left-one />
          <leftTwo />
        </div>
        <div class="center">
          <!-- 导航栏 -->
          <menuTip />
        </div>
        <div class="centerRight">
          <rightOne />
          <rightOne />
          <rightOne />
        </div>
      </div>
      <div class="right"></div>
    </div>
  </div>
</template>
<script>
import menuTip from "@/components/menu/index.vue";
import rightOne from "@/components/rightOne/index.vue";
import indexTop from "@/components/indexTop/index.vue";
import leftTwo from "@/components/leftTwo/index.vue";
import leftOne from "@/components/leftOne/index.vue";
export default {
  components: { indexTop, leftOne, leftTwo, rightOne, menuTip },
};
</script>

<style>
.largeScreen {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100%;
}
.indexTop {
  height: 6vh;
  background-color: cadetblue;
}
.box {
  margin: 5vh 0;
  width: 100%;
  height: 84vh;
  display: flex;
}
.left,
.right {
  width: 2%;
  height: 84vh;
}
.center {
  width: 100%;
  flex: 1;
  height: 84vh;
  display: flex;
}
.centerLeft {
  width: 25%;
  height: 84vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.centerRight {
  width: 25%;
  height: 84vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.none {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  /* background-color: aqua; */
}
.common {
  width: 100%;
  height: 27vh;
  background-color: yellow;
}
.rightTitle {
  font-size: 1.1vw;
}
</style>