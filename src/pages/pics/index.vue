<template>
  <div>
    <!-- <div class="mini-main"> -->
      <div class="loader">
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
      </div>
      
      <div class="loader">
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
        <div class="square"></div>
      </div>

      <ul>

        <li>百</li>

        <li>度</li>

        <li>经</li>

        <li>验</li>

        <li>好</li>

        <li>啊</li>
    
    </ul>
    <!-- </div> -->
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
    /* background: url('https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1571764850992&di=f2784554b86e40deb27391cc3578d414&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201807%2F09%2F20180709221054_ikysd.thumb.700_0.jpg'); */
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
* {
  -webkit-box-sizing: border-box;
     -moz-box-sizing: border-box;
          box-sizing: border-box;
}

/* The loader */
.loader {
  position: absolute;
  top: 50%;
  left: 50%;
  
  width: 200px;
  height: 200px;
  
  margin-top: -150px;
  margin-left: -100px;
  
  perspective: 600px;
  transform-style: perserve-3d;
}

/* The square */
.square {
  position: absolute;
  top: 50%;
  left: 50%;
  opacity: 0;
  
  width: 50px;
  height: 50px;
  
  margin-left: -25px;
  margin-top: 25px;
  
  background-color: #1e3f57;
  
  transform-style: perserve-3d;
  transform: rotateX(0deg) translateY(-100px);
  
  animation: square 5000ms linear infinite;
}

.loader:nth-child(2) .square { animation-name: square2; }

.square:nth-child(2) { animation-delay: 75ms; }
.square:nth-child(3) { animation-delay: 150ms; }
.square:nth-child(4) { animation-delay: 225ms; }
.square:nth-child(5) { animation-delay: 300ms; }
.square:nth-child(6) { animation-delay: 375ms; }
.square:nth-child(7) { animation-delay: 450ms; }
.square:nth-child(8) { animation-delay: 525ms; }
.square:nth-child(9) { animation-delay: 600ms; }
.square:nth-child(10) { animation-delay: 675ms; }
.square:nth-child(11) { animation-delay: 750ms; }
.square:nth-child(12) { animation-delay: 825ms; }
.square:nth-child(13) { animation-delay: 900ms; }
.square:nth-child(14) { animation-delay: 975ms; }
.square:nth-child(15) { animation-delay: 1050ms; }
.square:nth-child(16) { animation-delay: 1125ms; }
.square:nth-child(17) { animation-delay: 1200ms; }
.square:nth-child(18) { animation-delay: 1275ms; }
.square:nth-child(19) { animation-delay: 1350ms; }
.square:nth-child(20) { animation-delay: 1425ms; }
.square:nth-child(21) { animation-delay: 1500ms; }
.square:nth-child(22) { animation-delay: 1575ms; }
.square:nth-child(23) { animation-delay: 1650ms; }
.square:nth-child(24) { animation-delay: 1725ms; }
.square:nth-child(25) { animation-delay: 1800ms; }
.square:nth-child(26) { animation-delay: 1875ms; }
.square:nth-child(27) { animation-delay: 1950ms; }
.square:nth-child(28) { animation-delay: 2025ms; }
.square:nth-child(29) { animation-delay: 2100ms; }
.square:nth-child(30) { animation-delay: 2175ms; }
.square:nth-child(31) { animation-delay: 2250ms; }
.square:nth-child(32) { animation-delay: 2325ms; }
.square:nth-child(33) { animation-delay: 2400ms; }
.square:nth-child(34) { animation-delay: 2475ms; }
.square:nth-child(35) { animation-delay: 2550ms; }
.square:nth-child(36) { animation-delay: 2625ms; }

@keyframes square {
  0% {
    opacity: 0;
    background-color: #1e3f57;
    transform: rotateX(-180deg) translateY(-100px) translateZ(0px) rotateZ(0deg) scale(0.75);
  }
  25% {
    opacity: 1;
    background-color: #1e3f57;
    transform: rotateX(-90deg) translateY(-100px) translateZ(25px) rotateZ(90deg) scale(1.2);
  }
  50% {
    opacity: 0;
    background-color: #6bb2cd;
    transform: rotateX(0deg) translateY(-100px) translateZ(50px) rotateZ(180deg) scale(0.75);
  }
  75% {
    opacity: 1;
    background-color: #1e3f57;
    transform: rotateX(90deg) translateY(-100px) translateZ(25px) rotateZ(270deg) scale(0.5);
  }
  100% {
    opacity: 0;
    background-color: #1e3f57;
    transform: rotateX(180deg) translateY(-100px) translateZ(0px) rotateZ(360deg) scale(0.75);
  }
}

@keyframes square2 {
  0% {
    opacity: 0;
    background-color: #1e3f57;
    transform: rotateY(-180deg) translateX(-100px)translateZ(0px) rotateZ(0deg) scale(1);
  }
  25% {
    opacity: 1;
    background-color: #1e3f57;
    transform: rotateY(-90deg) translateX(-100px)translateZ(-25px) rotateZ(90deg) scale(0.5);
  }
  50% {
    opacity: 0;
    background-color: #6bb2cd;
    transform: rotateY(0deg) translateX(-100px)translateZ(-50px) rotateZ(180deg) scale(0.75);
  }
  75% {
    opacity: 1;
    background-color: #1e3f57;
    transform: rotateY(90deg) translateX(-100px)translateZ(-25px) rotateZ(270deg) scale(1.2);
  }
  100% {
    opacity: 0;
    background-color: #1e3f57;
    transform: rotateY(180deg) translateX(-100px)translateZ(0px) rotateZ(360deg) scale(1);
  }
}

ul {
        list-style: none;
    }
    ul {
        width:220px;
        height: 220px;
        margin: 220px auto;
        position: relative;
        transition: all 8s;
        transform-style: preserve-3d;
    }
    ul li {
        width: 100%;
        height: 100%;
        position: absolute;
        text-align: center;
        line-height: 150px;
        font-size: 40px;
        color: #000;
    }

    li:nth-child(1) {
        transform: rotateX(0deg) translateZ(110px);
        background-color: orange;
        opacity: 0.6;
    }

    li:nth-child(2) {
        transform: rotateX(90deg) translateZ(110px);
        background-color: yellow;
        opacity: 0.6;
    }

    li:nth-child(3){
        transform: rotateX(180deg) translateZ(110px);
        background-color: blue;
        opacity: 0.6;
    }
    li:nth-child(4){
        transform: rotateX(270deg) translateZ(110px);
        background-color: green;
        opacity: 0.6;
    }
    li:nth-child(5){
        transform: rotateY(-90deg) translateZ(110px);
        background-color: red;
        opacity: 0.6;
    }

    li:nth-child(6){
        transform: rotateY(90deg) translateZ(110px);
        background-color: purple;
        opacity: 0.6;
    }

    ul {
        transform :rotateX(360deg) rotateY(360deg);
    }
</style>
