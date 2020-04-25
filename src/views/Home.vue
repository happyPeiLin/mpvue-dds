<template>
  <div class="home">
    <div class="more8">
      <div class="header center-block clearfix">
        <a class="myHeaderL pull-left" href="/">
          <img src="../assets/xhy-logo.png" alt />
        </a>

        <div class="myHeaderR re">
          <div class="searchDiv">
            <input type="text" class="searchInput pull-left in" placeholder="请输入关键字" />
            <button class="searchButton"></button>
            <div class="searchRight ab">
              <a href="/" class="phone"></a>
              <span class="line">|</span>
              <a href="/" class="ftzWord">繁體版</a>
              <span class="line">|</span>
              <a href="/" class="weather"></a>
              <span class="line">|</span>
              <a href="/" class="robot"></a>
            </div>
          </div>

          <div class="my-login ab">
            <span class="hello pull-left">您好，请</span>
            <a class="my-dl" href="/">登录</a>
            <a class="my-zc" href="/">注册</a>
          </div>
        </div>
      </div>

      <div class="nav center-block">
        <div class="navs navs1">
          <a href="#">首页</a>
        </div>
        <div class="navs">
          <a href="#">政府领导</a>
        </div>
        <div class="navs">
          <a href="#">重庆发展</a>
        </div>
        <div class="navs">
          <a href="#">政务公开</a>
        </div>
        <div class="navs">
          <a href="#">渝快办</a>
        </div>
        <div class="navs">
          <a href="#">招商引资</a>
        </div>
        <div class="navs">
          <a href="#">重庆数据</a>
        </div>
        <div class="navs">
          <a href="#">互动交流</a>
        </div>
      </div>
      <div class="bar center-block"></div>

      <div class="change">
        <div class="changeLeft">
          <el-carousel arrow="never">
            <el-carousel-item v-for="item in list" :key="item.img">
              <img :src="item.img" />
              <div href="#" class="grey"></div>
              <a href="#" class="aaa">{{item.words}}</a>
            </el-carousel-item>
          </el-carousel>
        </div>
        <div class="changeRight">
          <ul class="crTop">
            <li :class="{crTopHover:switch1===1}">
              <a href="#">国务院信息</a>
            </li>
            <li>
              <a href="#">今日重庆</a>
            </li>
            <li>
              <a href="#">政务活动</a>
            </li>
          </ul>
          <div class="crBottom" v-show="switch1 === 1">
            <ul>
              <li class="text-left" v-for="(item,index) in gwyxx" :key="index">
                <a href="#">{{item.words}}</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <div class="less8">
      <div class="header8">
        <a href="#">
          <img src="../assets/xhy-logo.png" alt />
        </a>
      </div>
      <div class="nav8">
        <a href="#">政府领导</a>
        <div class="small-border"></div>
        <a class="margin-decrease" href="#">重庆发展</a>
        <div class="small-border"></div>
        <a class="margin-decrease" href="#">政务公开</a>
        <a href="#">渝快办</a>
        
        <div class="small-border"></div>
        <a class="margin-decrease" href="#">招商引资</a>
        
        <div class="small-border"></div>
        <a class="margin-decrease" href="#">互动交流</a>
      </div>

      <div class="changeLeft8">
        <el-carousel arrow="never" indicator-position="none" :height="elHeight + 'px'">
          <el-carousel-item v-for="item in list" :key="item.img">
            <img ref="imgs" :src="item.img" class="bannerImg" />
          </el-carousel-item>
        </el-carousel>
      </div>

      <div class="changeRight8">
        <ul class="crTop8">
          <li class="crTopHover">
            <a href="#">国务院信息</a>
          </li>
          <li>
            <a href="#">今日重庆</a>
          </li>
          <li>
            <a href="#">政务活动</a>
          </li>
        </ul>
        <div class="crBottom8">
          <ul>
            <li class="text-left" v-for="(item,index) in gwyxx" :key="index">
              <a href="#">{{item.words}}</a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import lkq from "../assets/lkq.jpg";
import xjp from "../assets/xjp.jpg";
import zy from "../assets/zhiyuan.jpg";
import wd from "../assets/tiwen.jpg";
import ys from "../assets/ys.jpg";
import fg from "../assets/fg.jpg";

export default {
  data: () => {
    return {
      changeCur: 0,
      switch1: 1,
      switch2: 1,
      elHeight: 205,
      gwyxx: [
        {
          words: "李克强考察这个平台后说：现在看来最终战胜疫情的曙光就要出现了"
        },
        { words: "李克强考察国家新冠肺炎药品医疗器械应急平台" },
        {
          words:
            "李克强主持召开中央应对新冠肺炎疫情工作领导小组会议 进一步部署降低病亡率和保障生活必需品供应等"
        },
        { words: "孙春兰：切实发挥支援湖北医务人员火线上的中流砥柱作用" },
        { words: "胡春华强调：全力做好稳外贸稳外资和生活必需品保供工作" },
        { words: "王毅：坚决打赢抗击疫情阻击战 推动构建人类命运共同体" },
        { words: "赵克志部署打击治理跨境赌博工作" }
      ],

      list: [
        {
          words: "春回大地耕作忙",
          img: xjp
        },
        { words: "志愿者助力抗疫情", img: lkq },
        { words: "驰援湖北 第十二批医疗队集结出发", img: zy },
        { words: "“智能人体测温系统”助力疫情防控", img: wd },
        { words: "复工复产保供应", img: fg },
        { words: "疑似病例在这里确诊 ——探访核酸检测实验室", img: ys }
      ]
    };
  },

  methods: {
    setSize() {
      this.elHeight = document.getElementsByClassName("bannerImg")[0].height;
      console.log(this.elHeight + "elHHH");
    }
  },

  mounted() {
    console.log("mouted");

    window.addEventListener("resize", this.setSize, false);
  }
};
</script>


<style>
@media only screen and (max-width: 800px) {
  html{
    font-size: 55%;
  }
  .more8 {
    display: none !important;
  }
  .less8 {
    display: block !important;
  }
}


.small-border {
  width: 1px;
  height:1.6rem;
  background-color: white;
  position: relative;
  display: inline-block;
  top: 3px;
}

.margin-decrease{

  margin-left: -1px;
}

.bannerImg {
  width: 100%;
}

.less8 {
  display: none;
}

.nav8 {
  width: 100%;
  background: linear-gradient(to top, #275394, #4678c5);
}

.nav8 a {
  display: inline-block;
  width: 33.33333%;
  font-size: 1.6rem;
  line-height: 3rem;
  color: white;
  text-decoration: none;
}
/* header */

.header {
  width: 1200px;
  height: 134px;
  background-color: #ffffff;
}

.myHeaderL {
  width: 599px;
  display: inline-block;
  height: 134px;
}

.myHeaderR {
  width: 588px;
  height: 134px;
  display: inline-block;
  vertical-align: top;
}
.searchDiv {
  width: 352px;
  height: 38px;
  border: 1px solid #4e9ddd;
  border-radius: 8px;
  margin-top: 53px;
  margin-left: 8px;
  overflow: hidden;
}
.searchInput {
  width: 285px;
  height: 100%;
  padding: 0 15px;
  box-sizing: border-box;
  border: none;
  outline: none;
  font-size: 16px;
}
.searchButton {
  width: 67px;
  height: 100%;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
  border-left: 1px solid #4e9ddd;
  background: #e9e8e8 url("../assets/search.jpg") center no-repeat;
}

.searchRight {
  top: 62px;
  left: 382px;
}

.phone {
  display: inline-block;
  width: 12px;
  height: 21px;
  background: url("../assets/phone.jpg") no-repeat;
  vertical-align: top;
}

.line {
  font-size: 14px;
  color: #999;
  padding: 0 10px;
  vertical-align: top;
}

.ftzWord {
  text-decoration: none;
  font-size: 14px;
  color: #275293;
  width: 46px;
}

.weather {
  display: inline-block;
  width: 22px;
  height: 23px;
  background: url("../assets/weather.png") no-repeat;
  vertical-align: top;
}

.robot {
  display: inline-block;
  width: 23px;
  height: 21px;
  background: url("../assets/robot.png") no-repeat;
  vertical-align: top;
}

.my-login {
  right: -5px;
  top: 12px;
}

.my-dl {
  color: #adadad;
  font-size: 16px;
  display: block;
  float: left;
  padding: 0 7px;
  border-right: 1px solid #adadad;
}

.my-zc {
  color: #adadad;
  font-size: 16px;
  display: block;
  float: left;
  padding: 0 7px;
}

.hello {
  font-size: 16px;
}

.nav {
  width: 1200px;
  height: 54px;
  background-color: yellow;
}
.bar {
  width: 100%;
  height: 6px;
  background-color: #0b67d4;
}
.main {
  width: 1200px;
  height: 400px;
  background-color: pink;
}

.re {
  position: relative;
}

.in {
  display: inline-block;
}

.ab {
  position: absolute;
}

/* nav */
.navs {
  width: 150px;
  height: 54px;
  display: inline-block;
  background-color: #f2f2f2;
  font-size: 2.2rem;
}

.navs a {
  vertical-align: middle;
  color: #2a6aa7;
  line-height: 2.5;
  text-decoration: none;
}

.navs1 {
  background: #275293;
}

.navs1 a {
  color: white;
}

/* change,main  */

.change {
  height: 36px;
  position: relative;

  width: 1200px;
  margin: 0 auto;
}
.changeLeft {
  width: 590px;
  height: 320px;
  position: absolute;
  top: 15px;
}

.changeLeft8 {
  width: 100%;
  top: 15px;
  margin-top: 10px;
}

.el-carousel__button {
  display: block;
  opacity: 0.48;
  width: 10px;
  height: 10px;
  background-color: #fff;
  border: none;
  outline: 0;
  padding: 0;
  margin: 0;
  cursor: pointer;
  left: 230;
  position: relative;
  border-radius: 5px;
}

el-carousel-item {
  position: relative;
}
.grey {
  display: inline-block;
  position: absolute;
  top: 280px;
  left: 0px;
  width: 1000px;
  height: 40px;
  background-color: black;
  opacity: 0.5;
  padding-top: 7px;
  padding-left: 20px;
  font-size: 1.8rem;
  color: white;
}
.aaa {
  display: inline-block;
  position: absolute;
  top: 280px;
  left: 0px;
  width: 200px;
  padding-top: 7px;
  padding-left: 20px;
  font-size: 1.8rem;
  color: white;
  text-decoration: none;
  overflow: hidden;
  text-overflow: ellipsis !important;
  white-space: nowrap;
}
.aaa:hover {
  text-decoration: underline;
}
.changeRight {
  background-color: white;
  position: relative;
  left: 610px;
  top: 0px;
  width: 585px;
  height: 320px;
}

.changeRight8 {
}

.crTop {
  list-style-type: none;
  float: left;
  padding: 0px;
  margin: 0px;
  height: 50px;
}

.crTop8 {
  width: 100%;

  list-style-type: none;
  float: left;
  padding: 0px;
  margin: 0px;
  height: 50px;
}
.crTopHover {
  border-bottom: 2px solid #2860b5 !important;
}
.crTop li {
  display: inline-block;
  background-color: white;
  width: 195px;
  height: 50px;
  text-align: center;
  vertical-align: middle;
  line-height: 50px;
  font-size: 2rem;
  border-bottom: 2px solid rgb(0, 162, 255);
}

.crTop8 li {
  display: inline-block;
  background-color: white;
  width: 33.33333%;
  height: 50px;
  text-align: center;
  vertical-align: middle;
  line-height: 50px;
  font-size: 2rem;
  border-bottom: 2px solid rgb(0, 162, 255);
}

.crTop li a {
  text-decoration: none;
  color: black;
}
.crBottom {
  width: 578px;
  height: 267px;
  background-color: white;
  position: relative;
  top: 53px;
  left: 19px;
  vertical-align: text-top;
}

.crBottom8 {
  width: 100%;
  height: 267px;
  background-color: white;
  position: relative;
  top: 53px;
  left: 19px;
  vertical-align: text-top;
}

.crBottom ul {
  position: absolute;
  display: block;
  text-decoration: none;
}

.crBottom8 ul {
  position: absolute;
  display: block;
  text-decoration: none;
}

.crBottom li {
  color: #cccccc;
  list-style-type: disc;
  line-height: 36px;
}

.crBottom8 li {
  color: #cccccc;
  list-style: disc !important;
  line-height: 36px;
  width: 90%;
}

.crBottom li a {
  line-height: 36px;
  text-decoration: none;
  color: black;
  font-size: 1.6rem;
  height: 36px !important;
  display: block;
  vertical-align: middle;
  display: inline;
}

.crBottom8 li a {
  line-height: 36px;
  text-decoration: none;
  color: black;
  font-size: 1.6rem;
  height: 36px !important;
  display: block;
  vertical-align: middle;
  display: inline;
}

.crBottom a:hover {
  text-decoration: underline;
}

/* header8 */
.header8 {
  width: 100%;
}

.header8 a {
  display: block;
}

.header8 a img {
  width: 100%;
  height: 100%;
}
</style>
