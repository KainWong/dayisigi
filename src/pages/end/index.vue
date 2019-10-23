<template>
  <div class="main">
    <div class="mini-main">
        <div @click="linkTo('../pic/main')">{{album}}</div>
        <div @click="linkTo('../logs/main')">{{words}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: '',
  data () {
    return {
        album: '相册簿',
        words: '悄悄话'
    }
  },

  watch: {
  },
  computed: {
  },
  create() {
  },
  methods: {
   linkTo(item) {
      const url = item;
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
  animation: disappear 2s
}

.dialog .message {
  padding:15rpx 20rpx;
  color: white;
  background: rgba(0,0,0,0.5);
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
