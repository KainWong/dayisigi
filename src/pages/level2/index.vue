<template>
<div class="main">
    <div class="mini-main">
        <div class="choose-title">{{question}}</div>
        <div class="choose-type" v-for="(item,index) in chooseList" :key="index" @click="nextLevel">{{item}}</div>
        <div class="dialog" v-if="showWarn">
        <div class="message">{{warnMessage}}</div>
        </div>
    </div>
</div>
</template>
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
    background: url('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1571723003978&di=f21df3fd97f2bbf67bf8e893524ee092&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201703%2F08%2F20170308124304_eNkzh.jpeg');
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
</style>
<script>
    export default {
        name: 'level2',
        components: {
        },
        props: {},
        data() {
            return {
                question: '看到一个小孩在旁边嚎啕大哭并惊声尖叫，你会什么反应？',
                chooseList: [
                    'A. 给他一拳',
                    'B. 一拳解决不了问题的话，再补上几拳',
                    'C. 这小孩太吵了，给多少拳都难以抚平我的烦躁'
                ]
            }
        },
        computed: {
        },
        watch: {
        },
        methods: {
            showWarnDialog(text) {
                this.warnMessage = text;
                this.showWarn = true;
                setTimeout(()=> {
                    this.showWarn = false
                },1500)
            },
            nextLevel() {
                this.showWarnDialog('没有最暴力，只有更暴力~');
                const url = '../level3/main';
                setTimeout(()=> {
                    wx.navigateTo({ url })
                },2000)
            }
        },
        created() {
        },
        destroyed() {
        },
        mounted() {
        }
    }
</script>