<template>
  <div class="main">
    <div class="mini-main">
      <div class="choose-title">{{summary}}</div>
      <div class="choose-type">A. 愿 意</div>
      <div class="choose-type">B. 不愿意</div>
    </div>
    <img class="poster" src="http://image109.360doc.com/DownloadImg/2018/08/1318/141247485_2_20180813064524787.gif" alt="">
  </div>
</template>

<script>
export default {
  name: '',
  data () {
    return {
      summary: '对不起啦宝贝，前面把你当成一个坏人是开玩笑的啦，感觉思维受限，我不知道要做些什么东西才好。我也不会编手链啥的，想想只能通过我在行的方式表达我的心意，虽然我也不知道你有没有感觉到开心（呜呜呜~）。而且我也不是设计，这个小程序我已经努力让它往好看的地方做了，就算你觉得丑也不要吐槽。以后我也会尝试学一些其他新的东西去取悦你，让你多点体验。如果你有一点感动的话，那我这两天花的时间也算没有白费，希望有吧。最后小马，我想问你，在以后人生中，你愿意和我一起体验各种不同的经历嘛？'
    }
  },

  watch: {
  },
  computed: {
  },
  create() {
  },
  methods: {
  },
  mounted() {
  }
}
</script>

<style lang='wxss'>
page {
  height: 100% !important;
}
.main {
  height: 100%;
  background-size: 100% 100%;
  position: relative;
}

.main:before {
    background: url('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1571764850992&di=f2784554b86e40deb27391cc3578d414&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201807%2F09%2F20180709221054_ikysd.thumb.700_0.jpg');
    background-size: 100% 100%;
    width: 100%;   
    height: 100%;          
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    z-index: -3;
    -webkit-filter:blur(2px);
    filter: blur(2px);
}

.poster {
  position: absolute;
  height: 100%;
  width: 100%;
  z-index: -1;
}

.main .mini-main {
  height: 100%;
  padding: 0 20rpx;
  position: absolute;
  overflow-y: scroll;
}

.dialog {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: disappear 2s
}

.dialog .message {
  padding:15rpx 20rpx;
  color: white;
  background: rgba(0,0,0,0.5);
}

.choose-title {
  font-size: 40rpx;
  color:maroon;
  font-family: LiSu;
  margin: 20rpx 0;
  margin-top: 100rpx;
  margin-bottom: 40rpx;
  text-align: left;
}

.choose-type {
  font-size: 40rpx;
  color:red;
  font-family: LiSu;
  margin: 20rpx 0;
  text-align: center;
}

@keyframes disappear {
  0%{
    opacity: 1
  }
  50%{
    opacity: 1
  }
  100% {
    opacity: 0;
  }
}
</style>
