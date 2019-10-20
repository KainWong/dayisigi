<template>
  <div class="main">
    <div class="mini-main">
      <div class="choose-title">请选择你是下列哪种类型？</div>
      <div class="choose-type" @click="showWarnDialog('那只是外表上的你，请你面对内心的自己')">A.清纯可爱型</div>
      <div class="choose-type" @click="showWarnDialog('你咋那么不要脸捏')">B.温柔知性型</div>
      <div class="choose-type" @click="showNext = true">C.憨批腹黑型</div>
    </div>
    <img class="poster" src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1571586247841&di=3c37df8d3bf69ca376b837e52c8864bf&imgtype=0&src=http%3A%2F%2Fimage109.360doc.com%2FDownloadImg%2F2018%2F08%2F1318%2F141247485_16_20180813064528834.gif" alt="">
    <div class="dialog-two" v-if="showNext">
      <div class="card">
        <div class="title">当你真正面对自己时，你才能知道你是谁，准备好接受下一个问题了吗</div>
        <div class="item" @click="nextLevel">A.什么破游戏，我不玩了</div>
        <div class="item" @click="nextLevel">B.好期待哦，我准备好了</div>
      </div>
      
    </div>
    <div class="dialog" v-if="showWarn">
      <div class="message">{{warnMessage}}</div>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      innerAudioContext: null,
      warnMessage: '',
      showWarn: false,
      showNext: false
    }
  },

  components: {
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      if (mpvuePlatform === 'wx') {
        mpvue.switchTab({ url })
      } else {
        mpvue.navigateTo({ url })
      }
    },
    showWarnDialog(text) {
      this.warnMessage = text;
      this.showWarn = true;
      setTimeout(()=> {
        this.showWarn = false
      },1500)
    },
    nextLevel() {
      this.showWarnDialog('既然你诚心发话了，那我就陪你玩下去吧');
      const url = '../level2/main'
      setTimeout(()=> {
        wx.navigateTo({ url })
      },2000)
    }
  },

  created () {
    this.innerAudioContext = wx.createInnerAudioContext();
    this.innerAudioContext.src = 'https://music.163.com/song?id=422429425&userid=55921888';
    this.innerAudioContext.onCanplay((res) => {
      console.log(1)
    })
  }
}
</script>

<style lang="wxss">
page{
  height: 100% !important;
}
.main {
  height: 100%;
  background-size: 100% 100%;
  position: relative;
}

.main:before {
    background: url('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1571563837508&di=1828c37922e0d25f6badcbf07b46b27a&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201510%2F05%2F20151005053743_hcFTr.thumb.700_0.jpeg');
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
  z-index: -1
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

.dialog-two {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.dialog-two .card {
  background: rgba(255,255,255,0.7);
  width: 80%;
  border-radius: 10rpx;
  border: 8rpx solid #f0ed49de;
  padding: 20rpx 15rpx;
}

.dialog-two .card .title {
  font-size: 35rpx;
  color:tomato;
  font-family: LiSu;
  margin: 15rpx 0;
}
.dialog-two .card .item {
  font-size: 30rpx;
  color:firebrick;
  font-family: LiSu;
  margin: 15rpx 0;
}

.dialog .message {
  padding:15rpx 20rpx;
  color: white;
  background: rgba(0,0,0,0.5);
}

.choose-title {
  font-size: 55rpx;
  color:orange;
  font-family: LiSu;
  margin: 20rpx 0;
  margin-top: 200rpx;
  margin-bottom: 40rpx;
  text-align: center;
}

.choose-type {
  font-size: 40rpx;
  color:orangered;
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
/* 
.choose-type:hover {
  background: rgba(255,255,255,0.3)
} */
</style>
