<template>
  <div class="main">
    <div class="mini-main">
        <div class="choose-title">{{question}}</div>
        <div class="choose-type" v-for="(item,index) in chooseList" :key="index" @click="nextLevel(index)">{{item}}</div>
    </div>
    <img class="poster" src="http://image109.360doc.com/DownloadImg/2018/08/1318/141247485_15_20180813064528444.gif" alt="">
    <div class="dialog" v-if="showWarn">
      <div class="message">{{warnMessage}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: '',
  data () {
    return {
        question: '你看到一个路人不小心滑倒摔了个屁股蹲儿，你会怎么做',
        chooseList: [
            'A. 赶忙跑上前去，询问情况',
            'B. 抑制住内心的喜悦，违心的发出怜悯“Oh,poor guy”',
            'C. 当场失控，笑得前仰后翻'
        ],
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
    nextLevel(index) {
      if(index == 0) {
        this.showWarnDialog('你并没有那么善良！');
        return; 
      }
      if(index == 2) {
        this.showWarnDialog('虽然这符合你的心理，但你还没那么敢');
        return; 
      }
      if(index == 1) {
        this.showWarnDialog('原来你真的是这种人');
        const url = '../level4/main'
        setTimeout(()=> {
          wx.navigateTo({ url })
        },2000)
      }
      
    }
  },
  mounted() {
  }
}
</script>

<style lang='wxss'>
page{
  height: 100% !important;
}
.main {
  height: 100%;
  background-size: 100% 100%;
  position: relative;
}

.main:before {
    background: url('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1571765156775&di=1476245fec73dc0d8fb0bdb196eb89c1&imgtype=0&src=http%3A%2F%2Fimg.nga.cn%2Fattachments%2Fmon_201612%2F05%2F-9lddQhfo-fkbkXhZ4rT3cSvm-1jk.jpg.thumb.jpg');
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

.dialog .message {
  padding:15rpx 20rpx;
  color: white;
  background: rgba(0,0,0,0.5);
}

.choose-title {
  font-size: 55rpx;
  color:blanchedalmond;
  font-family: LiSu;
  margin: 20rpx 0;
  margin-top: 200rpx;
  margin-bottom: 40rpx;
  text-align: center;
}

.choose-type {
  font-size: 40rpx;
  color:lawngreen;
  font-family: LiSu;
  margin: 20rpx 0;
  text-align: left;
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
