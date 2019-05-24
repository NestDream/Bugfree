<template>
  <div class="home">
    <div class="banner">
      <img alt="Vue logo" style="width: 64px; height: 64px" src="../assets/logo.png">
      <h3 style="margin-top: 1rem">王大毛，欢迎来到NKU-OPEP</h3>
    </div>
  <h2  align="center">新闻</h2>
<table border="1" align="center">
<tr>
<tr><td>张芳芳：10分钟之前提交了大数求和</td><td>查看详情</td></tr>
<tr><td>陈小小：20分钟之前获得了“解题小能手勋章”</td><td>查看详情</td></tr>
<tr><td>李大大：1天前成为排行棒第一的“霸主”，快来膜拜他！</td><td>查看详情</td></tr>
<tr><td>陈小小：1周前提交了B树实验</td><td>查看详情</td></tr>
<tr><td>周胖胖：2周前获得了“提交次数最多”勋章</td><td>查看详情</td></tr>
</tr>

</table>
    <br/>

  </div>
</template>

<script>
  // @ is an alias to /src

  import Trend from '@/components/Trend'
  import AvatarList from '@/components/AvatarList'
  import CountDown from '@/components/CountDown/CountDown'
  import Ellipsis from '@/components/Ellipsis'
  import NumberInfo from '@/components/NumberInfo'

  const AvatarListItem = AvatarList.AvatarItem

  export default {
    name: 'Home',
    components: {
      NumberInfo,
      Ellipsis,
      CountDown,
      Trend,
      AvatarList,
      AvatarListItem
    },
    data () {
      return {
        targetTime: new Date().getTime() + 3900000
      }
    },
    methods: {
      onEndHandle () {
        this.$message.success('CountDown callback!!!')
      },
      onEndHandle2 () {
        this.$notification.open({
          message: 'Notification Title',
          description: 'This is the content of the notification. This is the content of the notification. This is the content of the notification.',
        })
      }
    }
  }
</script>

<style scoped>
  .home {
    width: 900px;
    margin: 0 auto;
    padding: 25px 0;
  }
  .home > .banner {
    text-align: center;
    padding: 25px 0;
    margin: 25px 0;
  }
</style>
