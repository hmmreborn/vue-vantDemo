<template>
    <div class="address">
      <van-nav-bar
        title="地址"
        left-arrow
        @click-left="onClickLeft"
      />
      <van-address-list
        v-model="chosenAddressId"
        :list="list"
        @add="onAdd"
        @edit="onEdit"
      />
    </div>
</template>

<script>
import {Toast} from 'vant'
export default {
  name: 'AddressList',
  data () {
    return {
      chosenAddressId: '1',
      list: [
        {
          id: '1',
          name: '张三',
          tel: '13000000000',
          address: '浙江省杭州市西湖区文三路 138 号东方通信大厦 7 楼 501 室'
        },
        {
          id: '2',
          name: '李四',
          tel: '1310000000',
          address: '浙江省杭州市拱墅区莫干山路 50 号'
        }
      ],
      disabledList: [
        {
          id: '3',
          name: '王五',
          tel: '1320000000',
          address: '浙江省杭州市滨江区江南大道 15 号'
        }
      ]
    }
  },
  methods: {
    onClickLeft () {
      this.$router.go(-1)
    },
    onAdd () {
      this.$router.push('/addressEdit')
    },
    onEdit (item, index) {
      Toast('编辑地址:' + index)
    }
  }
}
</script>

<style scoped lang="scss">

</style>
