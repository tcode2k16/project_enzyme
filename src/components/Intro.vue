<template>
  <SwipeView>
    <div class="view v1">
        <Factory></Factory>
        <div class="text white">
          <h3>Our world is polluted</h3>
        </div>
      </div>
      <div class="view v2">
        <Fox></Fox>
        <div class="text">
          <h3>The animals are dying</h3>
        </div>
      </div>
      <div class="view v3">
        <Tree></Tree>
        <div class="text">
          <h3>The plants are suffering</h3>
        </div>
      </div>
      <div class="view v4">
        <Earth></Earth>
        <div class="text white">
          <h3>You can make a difference</h3>
          <div class="bt">Take action</div>
        </div>
      </div>
    </div>
  </SwipeView>
  </div>
</template>

<style scoped>

.v1 {
  background-color: #455;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.v2 {
  background-color: #f9ece8;
}

.v3 {
  background-color: #FEF2D8;
}

.v4 {
  background-color: #1B2B2F;
}


/*from http://codepen.io/thejamespower/pen/OVNYLL*/
.bt {
  margin: 10px auto;
  padding: 1vw;
  /*vertical-align: middle;*/
  border: 2px solid #f7f7f7;
  text-align: center;
  text-transform: uppercase;
  position: relative;
  overflow: hidden;
  transition: .3s;
  max-width: 300px;
  width: 20vw;
  min-width: 100px;
}
.bt:after {
  position: absolute;
  transition: .3s;
  content: '';
  width: 0;
  left: 50%;
  bottom: 0;
  height: 3px;
  background: #f7f7f7;
}
.bt:hover {
  cursor: pointer;
}
.bt:hover:after {
  width: 100%;
  left: 0;
}


</style>

<script>
import SwipeView from './SwipeView';
import Fox from './Intro/Fox';
import Factory from './Intro/Factory';
import Earth from './Intro/Earth';
import Tree from './Intro/Tree';

export default {
  components: { Fox, Factory, Earth, Tree, SwipeView },
};


</script>
