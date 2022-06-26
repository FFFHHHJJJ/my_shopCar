<template>
  <div class="my-counter">
    <button type="button" class="btn btn-light" @click="list.goods_count--">
      -
    </button>
    <input type="number" class="form-control inp" v-model="list.goods_count" />
    <button type="button" class="btn btn-light" @click="list.goods_count++">
      +
    </button>
  </div>
</template>

<script>
export default {
  props: {
    list: {
      type: Object,
      required: true
    }
  },
  watch: {
    list: {
      deep: true,
      immediate: true,
      handler() {
        if (this.list.goods_count <= 0) {
          this.list.goods_count = 0
        }
      }
    }
  }
}
</script>

<style lang="less" scoped>
.my-counter {
  display: flex;
  .inp {
    width: 45px;
    text-align: center;
    margin: 0 10px;
  }
  .btn,
  .inp {
    transform: scale(0.9);
  }
}
</style>
