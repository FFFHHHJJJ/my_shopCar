<template>
  <div class="app">
    <Myheader title="购物车案例" color='black'></Myheader>
    <MyGoods></MyGoods>
    <MyFooter></MyFooter>
  </div>
</template>

<script>
import Myheader from '@/components/Myheader'
import MyGoods from '@/components/MyGoods'
import MyFooter from '@/components/MyFooter'
export default {
  components: {
    Myheader,
    MyGoods,
    MyFooter
  }
  // data() {}
}
</script>

<style>
.app {
  padding: 45px 0;
}
</style>
