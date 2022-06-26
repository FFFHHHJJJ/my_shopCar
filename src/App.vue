<template>
  <div class="app">
    <Myheader title="购物车案例" color="black"></Myheader>
    <MyGoods
      v-for="item in GoodList"
      :key="item.goods_id"
      :list="item"
    ></MyGoods>
    <MyFooter :list="GoodList"></MyFooter>
  </div>
</template>
GoodList
<script>
import Myheader from '@/components/Myheader'
import MyGoods from '@/components/MyGoods'
import MyFooter from '@/components/MyFooter'
import axios from 'axios'
export default {
  components: {
    Myheader,
    MyGoods,
    MyFooter
  },
  data() {
    return {
      GoodList: []
    }
  },
  created() {
    this.getGoods()
  },
  methods: {
    async getGoods() {
      const res = await axios({ url: '/api/cart' })
      this.GoodList = res.data.list
    }
  }
}
</script>

<style>
.app {
  padding: 45px 0;
}
</style>
