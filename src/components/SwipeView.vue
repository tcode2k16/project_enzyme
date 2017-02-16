<template>
  <div class="swipe">
  
    <div class="main">
      <slot></slot>
    </div>
    <ProgressBar :before="before" :next="next"></ProgressBar>
  </div>
</template>

<style scoped>


.text {
  text-align: center;
  position: absolute;
  display: block;
  top: 70%;
  width: 100vw;
  z-index: 100;
}

.white {
  color: #fff;
}

.view {
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

.swipe {
  display: block;
  position: relative;
  background: black;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}
.main {
  display: flex;
  height: 100vh;
  transition: transform 0.3s;
  
}


</style>

<script>

import $ from 'jquery';
import Hammer from 'hammerjs';
import ProgressBar from './ProgressBar';

export default {
  components: { ProgressBar },
  data() {
    return {
      main: null,
      len: 0,
      transform: 0,
    };
  },
  mounted() {
    this.main = new Hammer($('.swipe')[0]);
    this.len = $('.main>.view').length;
    $('.main').css('width', `${this.len}00vw`);


    this.main.on('swipeleft', this.next);

    this.main.on('swiperight', this.before);
  },
  methods: {
    before() {
      this.transform = Math.min(0, this.transform + 1);
      this.update();
    },
    next() {
      this.transform = Math.max(-this.len + 1, this.transform - 1);
      this.update();
    },
    update() {
      $('.main').css('transform', `translate(${this.transform}00vw,0px)`);
    },
  },
};


</script>
