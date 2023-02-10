<template>
  <div class="indexContainer">
      <largeScreen/>
  </div>
</template>
<script>
import largeScreen from '@/components/largeScreen/index.vue'
export default {
  components: {largeScreen},
  name: "Login"
};
</script>
<style lang="scss" scoped>
.indexContainer{
  height: 100vh;
  /* background-color: cadetblue; */
}
</style>
