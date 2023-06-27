<template>
  <div class="NavBar">
    <div class="info-bar-wrapper">
      <div class="info-bar">
        <p> * 본 페이지는 상업적인 용도로 제작된 페이지가 아닙니다.</p>
        <ul class="info-list">
          <li class="info-item" v-for="(a, i) in infoData" :key="i"><a href="">{{ a }}</a></li>
        </ul>
      </div>
    </div>
    <div class="nav-wrapper">
      <div class="logo-box">
        <a href=""><img class="logo" src="../assets/images/logo.png" alt="logo"></a>
      </div>
      <div class="nav-list-wrapper">
        <ul class="nav-list" v-on:mouseleave="mouseNotOverEvent()">
          <li class="nav-list-item" v-for="(a, i) in navData" :key="i">
            <a href="" v-on:mouseover="mouseOverEvent(i)">{{ a.menuTitle }}</a>
            <div class="nav-item-box" :class="isRightId === i ? 'on' : ''">
              <ul class="nav-item-list">
                <li class="nav-item-inner">
                  <a href="" v-for="(a, i) in navData[i].itemTitle" :key="i">{{ a }}</a>
                </li>
              </ul>
            </div>
          </li>
        </ul>
        <button class="csBtn">
          <p><font-awesome-icon style="font-size: .8rem; margin-right: 5px;" :icon="['fas', 'phone']" /> 전문상담</p>
        </button>
      </div>
      <div class="null-box"></div>
    </div>
  </div>
</template>
<script>

import navData from '../assets/data.js'

export default {
  name: 'NavBar',
  props: {
    
  },
  methods: {
    mouseOverEvent(i) {
      this.isRightId = i;
    },
    mouseNotOverEvent() {
      this.isRightId = null;
    }
  },
  data() {
    return {
      navData: navData,
      infoData: ['HOME', 'FMS Demo 보기', '원격지원'],
      isRightId: null,
    }
  },
}
</script>
<style>
  .NavBar {
    width: 100%;
    background-color: #fff;
  }

  .info-bar-wrapper {
    width: 100%;
    background-color: #1b1b1b;
    color: #d1d1d1;
  }

  .info-bar {
    width: 70%;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    font-size: 0.9rem;
  }

  .info-bar p {
    margin-right: 50px;
  }

  .info-item {
    margin-right: 10px;
  }

  .info-item:first-child::after,
  .info-item:nth-child(2)::after {
    content: '｜';
    margin-left: 5px;
  }

  .info-list {
    display: flex;
    padding: 20px;
    list-style: none;
  }

  .nav-wrapper {
    width: 100%;
    display: flex;
    align-items: center;
    border-bottom: 1px solid rgba(0, 0, 0, 0.623);
    box-sizing: border-box;
  }

  .logo-box {
    width: 30%;
    height: 68px;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding: 5px 0;
  }

  .logo {
    width: 190px;
    padding-right: 20px;
  }

  .nav-list-wrapper {
    width: 60%;
    height: 68px;
    display: flex;
    align-items: center;
    justify-content: space-around;
    background-color: #ac1b1d;
    color: #fff;
    padding: 5px 0;
  }

  .nav-list {
    display: flex;
    list-style: none;
    padding: 17px 0;
  }

  .nav-list-item {
    position: relative;
    margin: 0 15px;
    padding: 5px;
  }

  .nav-list-item a {
    padding: 10px 0;
  }

  .nav-list-item::before {
    content: '＿';
    position: absolute;
    font-size: .4rem;
    top: 15px;
    left: 8px;
    transition: opacity .5s;
  }

  .nav-item-box {
    width: 230px;
    position: absolute;
    opacity: 0;
    z-index: -1;
    top: 60px;
    left: -14px;
    border: .5px solid #0000003a;
    background-color: #fff;
    color: black;
    box-shadow: .5px .5px .5px .5px #0000002c;
    transition: top .5s, opacity .5s;
  }

  .nav-item-box.on {
    opacity: 1;
    top: 40px;
    z-index: 1;
  }

  .nav-item-inner {
    display: flex;
    flex-direction: column;
    list-style: none;
  }

  .nav-item-inner a {
    z-index: 2;
    padding: 10px 20px;
    border-bottom: 1px solid #00000010;
  }

  .nav-item-inner a:hover {
    background-color: #c4c4c4;
  }

  .nav-item-inner a:first-child::before {
    content: '';
    position: absolute;
    top: -5px;
    width: 10px;
    height: 10px;
    background-color: #fff;
    /* border: 1px solid red; */
    transform: rotate(45deg);
  }

  .nav-item-inner a:hover:first-child::before {
    background-color: #c4c4c4;
  }

  .nav-list-item:hover::before {
    opacity: .3;
  }

  .csBtn {
    padding: 15px 25px;
    background-color: #ac1b1d;
    border-radius: 30px;
    border: none;
    color: #fff;
    font-size: .9rem;
    transition: background-color .3s;
    cursor: pointer;
  }

  .csBtn:hover {
    background-color: #af4244;
  }

  .null-box {
    width: 10%;
    height: 68px;
    background-color: #ac1b1d;
    padding: 5px 0;
  }
</style>