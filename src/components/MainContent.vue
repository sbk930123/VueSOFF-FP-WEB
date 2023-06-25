<template>
  <div class="info-main-wrapper">

    <div class="bg-black" :class="isMouseOver ? 'on' : ''"></div>

    <div class="info-text-box" :class="isMouseOver ? 'on' : ''" v-for="(a, i) in infoData" :key="i">
      <div class="info-data-wrapper">
        <p class="info-title">
          {{ infoData[isRightId].title }}
          <span>{{ infoData[isRightId].subTitle }}</span>
        </p>
        <p class="info-text">
          {{ infoData[isRightId].infoText }}
        </p>
      </div>
    </div>

    <div class="info-btn-wrapper">
      <div class="btn-box-left" v-on:mouseover="mouseOverEvent(0)" v-on:mouseleave="mouseNotOverEvent()">
        <div class="btn-box-left-item">
          <p class="btn-text-title" style="font-size: 2rem; line-height: 25px; padding: 20px; margin: 20px 0 0 13px;">
            {{ infoData[0].title }}<br>
            <span style="font-size: 1rem; color: #cccccc;">{{ infoData[0].subTitle }}</span>
          </p>
        </div>
        <img class="img-icon" src="../assets/images/sicon.png" alt="">
      </div>
      <div class="btn-box-right">
        <div class="btn-box-right-up" v-on:mouseover="mouseOverEvent(1)" v-on:mouseleave="mouseNotOverEvent()">
          <p class="right-text-title">
            {{ infoData[1].title }}<br>
            <span>{{ infoData[1].subTitle }}</span>
          </p>
          <img style="margin-right: 40px;" class="right-icon" src="../assets/images/bizcon.png" alt="">
        </div>
        <div class="btn-box-right-down">
          <div class="btn-box-right-down-item1" v-on:mouseover="mouseOverEvent(2)" v-on:mouseleave="mouseNotOverEvent()">
            <p class="right-text-down-title">
              {{ infoData[2].title }}<br>
              <span>{{ infoData[2].subTitle }}</span>
            </p>
            <img class="right-down-icon" src="../assets/images/itcon.png" alt="">
          </div>
          <div class="btn-box-right-down-item2" v-on:mouseover="mouseOverEvent(3)" v-on:mouseleave="mouseNotOverEvent()">
            <p class="right-text-down-title">
              {{ infoData[3].title }}<br>
              <span>{{ infoData[3].subTitle }}</span>
            </p>
            <img class="right-down-icon" src="../assets/images/comcon.png" alt="">
          </div>
        </div>
      </div>
    </div>

    <div class="img-box">
      <div><img :src="`${infoData[isRightId].imgSrc}`" alt=""></div>
    </div>
    
  </div>
</template>

<script>

import infoData from '@/assets/infoData';

export default {
  name: 'MainContentVue',
  data() {
    return {
      infoData : infoData,
      isRightId : 0,
      isMouseOver : false,
    }
  },
  methods: {
    mouseOverEvent(e) {
      this.isMouseOver = true;
      this.isRightId = e;
    },

    mouseNotOverEvent() {
      this.isMouseOver = false;
    }
  }
}
</script>

<style>
  .info-main-wrapper {
    width: 100%;
    position: relative;
  }

  .bg-black {
    position: absolute;
    width: 100%;
    height: 750px;
    background-color: black;
    opacity: 0;
    transition: opacity .5s;
  }

  .bg-black.on {
    opacity: .7;
  }

  .info-text-box {
    position: absolute;
    width: 40%;
    left: 50%;
    transform: translateX(-50%);
    top: 100px;
    opacity: 0;
    transition: opacity .3s ease-in-out;
    user-select: none;
  }

  .info-text-box.on {
    opacity: 1;
  }

  .info-title {
    font-size: 3rem; color: #fff;
    text-shadow: 1px 1px 1px #474747;
  }

  .info-title span {
    font-size: 1.2rem;
    color: #cccccc;
  }

  .info-text {
    width: 100%; transform: translateX(20px);
    font-size: 1.1rem;
    margin-top: 20px;
    color: #fff;
    line-height: 35px;
    text-shadow: 1px 1px 1px #474747;
  }

  .info-btn-wrapper {
    position: absolute;
    display: flex;
    width: 820px;
    height: 320px;
    left: 50%;
    transform: translateX(-50%);
    bottom: 50px;
    padding: 10px;
    color: #fff;
    user-select: none;
  }

  .btn-box-left {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 340px;
    height: 100%;
    border: 3px solid #fff;
    background-color: #00000050;
    box-shadow: 1px 1px 1px black;
    cursor: pointer;
  }

  .btn-box-left:hover {
    background-color: #663399b3;
  }

  .img-icon {
    width: 180px;
    padding-left: 10px;
  }

  .right-icon {
    height: 120px;
  }

  .btn-box-right {
    width: 480px;
    height: 100%;
    margin-left: 10px;
  }

  .btn-box-right-up {
    height: 145px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 3px solid #fff;
    background-color: #00000050;
    box-shadow: 1px 1px 1px black;
    margin-bottom: 10px;
    cursor: pointer;
  }

  .btn-box-right-up:hover {
    background-color: #ffa600b3;
  }

  .right-text-title {
    margin-left: 40px;
    font-size: 1.5rem;
  }

  .right-text-title span {
    font-size: 1rem;
    color: #cccccc;
  }

  .btn-box-right-down {
    height: 145px;
    display: flex;
    box-shadow: 1px 1px 1px black;
  }

  .btn-box-right-down-item1 {
    width: 235px;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 3px solid #fff;
    box-shadow: 1px 1px 1px black;
    background-color: #00000050;
    margin-right: 10px;
    cursor: pointer;
  }

  .btn-box-right-down-item1:hover {
    background-color: #1e8fffb3;
  }

  .btn-box-right-down-item2 {
    width: 235px;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border: 3px solid #fff;
    background-color: #00000050;
    box-shadow: 1px 1px 1px black;
    cursor: pointer;
  }

  .btn-box-right-down-item2:hover {
    background-color: #acff2fb3;
  }

  .right-text-down-title {
    font-size: 1.2rem;
    margin-left: 20px;
  }

  .right-text-down-title span {
    font-size: .7rem;
    color: #cccccc;
  }

  .right-down-icon {
    height: 90px;
    margin-right: 10px;
  }

  .img-box img {
    width: 100%;
    height: 750px;
  }
</style>