<template>
  <div class="swipe">
  
    <div class="main">
      <slot></slot>
    </div>
    <slot name="bar"></slot>
  </div>
</template>

<style scoped>

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

export default {
  data() {
    return {
      main: null,
      len: 0,
      transform: 0,
    };
  },
  mounted() {
    this.main = new Hammer($('.intro')[0]);
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
