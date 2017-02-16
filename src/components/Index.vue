<template>
  <SwipeView :bar="false">
    <div class="view v1">
      <Christmas></Christmas>
      <div class="text white">
        <h3 class="title">Daily Challenge</h3>
        <div class="bt">
          Next
          <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </div>
      </div>
    </div>
    <div class="view v2">

    </div>
    <div class="view v3">

    </div>
  </SwipeView>
</template>

<script>
import SwipeView from './SwipeView';
import Christmas from './Index/Christmas';

export default {
  components: { SwipeView, Christmas },
};
</script>

<style scoped>
.title {
  text-align: center;

}

.v1 {
  background-color: #1B2B2F;
}

.v2 {
  background-color: #f00;
}

.v3 {
  background-color: #ff0;
}

</style>

