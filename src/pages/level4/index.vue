<template>
  <div class="main">
    <div class="mini-main">
      <div class="choose-title">{{summary}}</div>
      <div class="choose-type" @click="nextLevel('你就像那黑暗的石矶娘娘')">A. 是的</div>
      <div class="choose-type" @click="nextLevel('那你就是更关注妲己喽')">B. 不是</div>
    </div>
    <img class="poster" src="" alt="">
  </div>
</template>

<script>
export default {
  name: '',
  data () {
    return {
      summary: '小时候看哪吒传奇动画片你是不是更注意石矶娘娘这种反派角色？',
      showWarn: false,
      warnMessage: ''
    }
  },

  watch: {
  },
  computed: {
  },
  create() {
  },
  methods: {
    showWarnDialog(text) {
        this.warnMessage = text;
        this.showWarn = true;
        setTimeout(()=> {
            this.showWarn = false
        },1500)
    },
    nextLevel(text) {
        this.showWarnDialog(text);
        const url = '../level3/main';
        setTimeout(()=> {
            wx.navigateTo({ url })
        },2000)
    }
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
  animation: disappear 2s;
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
