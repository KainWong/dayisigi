<template>
  <div class="main">
    <div class="mini-main">
      <div class="title">有些事还要你多多包涵啦：</div>
      <p class="explain" v-for="(item,index) in  sorryList" :key="index">{{item}}</p>
      <div class="result">对于上面这些问题，我想说我会尽力去改的，嘻嘻。</div>
      <div class="arrow-line">{{arrowLine}}</div>
      <div class="title">我特别喜欢你一些可爱瞬间：</div>
      <p class="explain" v-for="(item,index) in  adroableList" :key="index">{{item}}</p>
      <div class="result">这样一看怎么感觉都是你的糗事，不过在我眼里就是可爱，嘻嘻嘻。</div>
      <div class="arrow-line">{{arrowLine}}</div>
      <div class="title">你也要好好照顾自己哦：</div>
      <p class="explain" v-for="(item,index) in  careselfList" :key="index">{{item}}</p>
      <div class="result">只有你好好照顾自己了，这样当爸爸的我也就少操了一份心，嘻嘻嘻嘻。</div>
      <div class="more-words">{{moreWords}}</div>
      <div class="summary">{{iou}}</div>
      <div class="love-react">
        <div>❣&nbsp; ❣ &nbsp;❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣</div>
        <div style="display:flex;justify-content:space-between"><span>❣</span><span style="margin-right:5rpx">❣</span></div>
        <div style="display:flex;justify-content:space-between"><span>❣</span>      <span>爱你，么么哒！</span>       <span style="margin-right:5rpx">❣</span></div>
        <div style="display:flex;justify-content:space-between"><span>❣</span><span style="margin-right:5rpx">❣</span></div>
        <div>❣&nbsp; ❣ &nbsp;❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣&nbsp; ❣</div>
      </div>
    </div>
  </div>
</template>

<script>
import { formatTime } from '@/utils/index'
import card from '@/components/card'

export default {
  components: {
    card
  },

  data () {
    return {
     sorryList: [
       '☹ 坐车来看我那天，因为多次堵车让你在车上感到焦躁，而我却躺在床上不小心睡着，忽略了你的感受，没有陪你。',
       '☹ 和你在一起的时候经常要你打开话题，你还是会不厌其烦的和我聊一些你身边的事，让你费心了。',
       '☹ 收到你亲手编织的手链和你写的信，你埋怨我没有表达心意。其实我心里真的有种前所未有的喜悦，只是我不善表达。',
       '☹ 你说我很会撒娇，要你经常哄我（那你以后跟我撒娇呗）'
     ],
     adroableList: [
       '☺ 当你知道我怕痒，你会不时的突袭我的咯吱窝，口区，真想把你摁在地上摩擦。',
       '☺ 你唱歌或者唱戏曲的时候。',
       '☺ 你穿上粉红色妈妈睡衣的时候。',
       '☺ 最可爱的当然就是你学生时代跟别人打架的时候了，明明打不过还硬要哭着继续犟下去。',
     ],
     careselfList: [
       '㋡ 平时自己多吃点，长点肉肉。',
       '㋡ 最近你睡觉太晚啦，希望你能像以前一样早点睡。',
       '㋡ 空闲的时候看会儿书，做个努力的girl。',
       '㋡ 最近天冷也要记得多穿点，别冻着感冒哦。'
     ],
     iou: '私は本当にあなたが大好きです',
     arrowLine: '➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ➤ ',
     moreWords: '  其实我有好多话想和你说，比如你也是个jinv。为了宠你我也做了退步，让你比我好看了。还有你说我是没有感情的，只能说你观察我还不够仔细，我的小心思有时候比你想象的还复杂。说我憨批的时候你也要想想自己是不是（指责我，你不配.jpg），你说我要爱你多一点点，关键这个多和少的衡量标准是什么啊，喂小老弟你也不知道吧。最后我想说我当然会试着比之前还要多爱你一些，了解你更深一些，我想要我们更开心。'
    }
  },

  created () {
    let logs
    if (mpvuePlatform === 'my') {
      logs = mpvue.getStorageSync({key: 'logs'}).data || []
    } else {
      logs = mpvue.getStorageSync('logs') || []
    }
    this.logs = logs.map(log => formatTime(new Date(log)))
  }
}
</script>

<style lang="wxss">
.main {
  height: 100%;
  background-size: 100% 100%;
  position: relative;
}

.main:before {
    background: url('https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3575167888,2720496953&fm=26&gp=0.jpg');
    background-size: 100% 100%;
    width: 100%;   
    height: 100%;          
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
    -webkit-filter:blur(2px);
    filter: blur(2px);
}

.main .mini-main {
  height: 100%;
  padding: 0 20rpx;
  position: absolute;
  overflow-y: scroll;
}
.main .title {
  font-size: 55rpx;
  color:cadetblue;
  font-family: LiSu;
  margin: 20rpx 0;
}

.main .result {
  font-size: 40rpx;
  color:cadetblue;
  font-family: LiSu;
  margin: 20rpx 0;
}
.main .explain {
  color: aqua;
  font-family: KaiTi;
  margin: 15rpx 0;
}

.main .summary {
  font-size: 65rpx;
  color:pink;
  font-family: SimHei;
  margin: 40rpx 0;
  text-align: center;
  padding: 0 50rpx;
}

.main .arrow-line {
  color:dodgerblue;
  font-family: KaiTi;
  margin: 15rpx 0;
  font-size: 25rpx;
}

.main .love-react {
  color: crimson;
  font-size: 40rpx;
  font-weight: 500;
  padding: 20rpx 40rpx;
}

.main .more-words {
  font-size: 45rpx;
  color:forestgreen;
  font-family: LiSu;
  margin: 20rpx 0;
}
page{
  height: 100% !important;
}
</style>
