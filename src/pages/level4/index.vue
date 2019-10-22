<template>
  <div class="main">
    <div class="mini-main">
        <div></div>
    </div>
  </div>
</template>

<script>
export default {
  name: '',
  data () {
    return {

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
