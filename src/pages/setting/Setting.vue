<template>
  <div>
    <div class="user-poster">
      user
    </div>
    <van-row class="user-links">
      <van-col span="6">
        <van-icon name="pending-payment" />
        待付款
      </van-col>
      <van-col span="6">
        <van-icon name="records" />
        待接单
      </van-col>
      <van-col span="6">
        <van-icon name="tosend" />
        待发货
      </van-col>
      <van-col span="6">
        <van-icon name="logistics" />
        已发货
      </van-col>
    </van-row>

    <van-cell-group class="user-group">
      <van-cell icon="records" title="全部订单" is-link replace to="/order"/>
    </van-cell-group>
    <van-cell-group>
      <van-cell icon="gift-o" title="地址管理" is-link to="/address"/>
      <van-cell icon="points" title="我的积分" is-link />
      <van-cell icon="gold-coin-o" title="我的优惠券" is-link />
    </van-cell-group>
    <van-tabbar v-model="tabarActive">
      <van-tabbar-item name="home" icon="home-o" replace to="/">首页</van-tabbar-item>
      <van-tabbar-item name="list" icon="apps-o" replace to="/list">分类</van-tabbar-item>
      <van-tabbar-item name="shopping" icon="shopping-cart-o" replace to="/shopping" info="1">购物车</van-tabbar-item>
      <van-tabbar-item name="setting" icon="contact" replace to="/setting">我的</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
import { Row, Col, Icon, Cell, CellGroup } from 'vant'
export default {
  name: 'Setting',
  components: {
    [Row.name]: Row,
    [Col.name]: Col,
    [Icon.name]: Icon,
    [Cell.name]: Cell,
    [CellGroup.name]: CellGroup
  },
  data () {
    return {
      tabarActive: 'setting'
    }
  },
  methods: {
  }
}
</script>

<style lang="scss" scoped>
  .user {
    &-poster {
      width: 100%;
      height: 53vw;
      display: block;
      background-image: linear-gradient(to top, #a8edea 0%, #fed6e3 100%);
    }
    &-group {
      margin-bottom: 15px;
    }
    &-links {
      padding: 15px 0;
      font-size: 12px;
      text-align: center;
      background-color: #fff;
      .van-icon {
        display: block;
        font-size: 24px;
      }
    }
  }
</style>
