<template>
  <div id="app">
    <div class="nav">
      
      <div class="logo"><img src="./assets/logo1.png" alt=""></div>
      <div class="bars">
        <ul>

          <!--<li @click="slideto(0)">主页</li>
            <li @click="slideto(0)">项目</li>
            <li @click="slideto(0)">资料</li>
            <li @click="slideto(0)">关于我</li>-->
          <li v-for="(bar,index) in bars" @click="slideto(index)">{{bar}}</li>

        </ul>
      </div>
    </div>
    <div class="swiper-container">
      <div class="swiper-wrapper">

        <div class="swiper-slide">
          <img class="imgload" src="./assets/001.jpg" alt="首页banner图片01">
        </div>
        <div class="swiper-slide">
          <img class="imgload" src="./assets/002.jpeg" alt="首页banner图片01">
        </div>
        <div class="swiper-slide">
          <img class="imgload" src="./assets/003.jpg" alt="首页banner图片01">
        </div>
        <div class="swiper-slide">
          <img class="imgload" src="./assets/004.jpeg" alt="首页banner图片01">
        </div>
  
      
      </div>
      <!-- 如果需要分页器 -->
      <div class="swiper-pagination"></div>

    </div>
  </div>
</template>

<script>
import Swiper from './../static/swiper.min.js'
require('./../static/swiper.min.css')

export default {
  components: {},
  data() {
    return {
      bars: ["主页", "项目", "资料", "关于我"],
      swiper: null
    }
  },
  mounted() {
    console.log('挂载好了')
    var swiper = new Swiper('.swiper-container', {
      pagination: '.swiper-pagination',
      direction: 'vertical',
      slidesPerView: 1,
      paginationClickable: true,
      // spaceBetween: 0,
      mousewheelControl: true
    });
    this.swiper = swiper;
    // this.slideto(swiper)
  },
  methods: {
    slideto: function(index) {
      this.swiper.slideTo(index, 1000, false);

    }
  }
}



</script>

<style>
html,
body {
  /*position: relative;*/
  height: 100%;
}

ul {
  list-style: none;
}

body {
  background: #eee;
  font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
  font-size: 14px;
  color: #000;
  margin: 0;
  padding: 0;
}

.swiper-container {
  width: 100%;
  height: 100%;
  margin-left: auto;
  margin-right: auto;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: -webkit-radial-gradient(#33342c, #282a21);
  /* Safari 5.1 - 6.0 */
  background: -o-radial-gradient(#33342c, #282a21);
  /* Opera 11.6 - 12.0 */
  background: -moz-radial-gradient(#33342c, #282a21);
  /* Firefox 3.6 - 15 */
  background: radial-gradient(#33342c, #282a21);
  /* 标准的语法 */
  /* Center slide text vertically */
  display: -webkit-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  -webkit-align-items: center;
  align-items: center;
}

.swiper-slide img {
  width: 100%;
  height: 100%;
}

#app {
  color: #2c3e50;
  /*margin-top: -100px;*/
  /*max-width: 600px;*/
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
  height: 100%;
  position: relative;
}

#app a {
  color: #42b983;
  text-decoration: none;
}


.nav {
  position: fixed;
  height: 50px;
  width: 100%;
  /*line-height: 50px;*/
  top: 0;
  left: 0;
  z-index: 2;
  /*background:#ccc;*/
}

.logo {
  float: left;
  height: 100%
}

.logo img {
  height: inherit;
}

.bars {
  float: right;
}

.bars ul li {
  width: 50px;
  /*height: 100%;*/
  float: left;

  color: #ffffff;
}

.bars ul li:hover {
  cursor: pointer;
}
</style>
